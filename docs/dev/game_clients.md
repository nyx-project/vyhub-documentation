# Guideline for game clients

This guide explains how a VyHub game client should be structured.

> This guide may contain typos and other mistakes, because it is not completely finished yet. 

Example implementation for Garry's Mod (Lua): https://github.com/matbyte-com/vyhub-gmod

## Concepts

### Events
If possible, own events should be introduced and named as follows:

- `vyhub_loading_start`: Called when addon is loading.
- `vyhub_loading_finish`: Called when addon has finished loading.
- `vyhub_api_ready`: API client is ready and API is reachable.
- `vyhub_api_failed`: API client is not ready because API is not reachable.
- `vyhub_ready`: Server information has been loaded from the API or cache.
- `vyhub_ply_connected`: Called when a player connected but is not initialized yet.
- `vyhub_ply_initialized`: Called when a player has been successfully initialized (user retrieved from API).

For application start it should be:

`vyhub_loading_start` -> `vyhub_loading_finish` -> `vyhub_api_ready`/`vyhub_api_failed` -> `vyhub_ready`

## morph_user_id
Some endpoints (f.e. when creating bans or warnings) support the `morph_user_id` parameter. If the parameter is set
with a user id, the request will be executed as the user which id has been supplied.

This has the advantage that permission checks must not be implemented on the client side and allows the server
to act on behalf of the user.

**If the `morph_user_id` parameter is omitted, a security/permission check must be done on the client before sending the request!**

## Server
### Config
The server needs three values to work:

- API URL
- API Key
- Server ID

There should be a config where the admin can insert the values.

### Startup
- When the addon is loaded, the server should request information about itself and its serverbundle:

> `GET /server/<id>`, where `<id>` is the server id from the config.

- Save this information for the runtime of the server and permanently save it to a cache.

- If the API server is not available, use the data from the cache if the last successful retrieval is not older than a week.

- Start the routines/register the event listeners of the following components afterwards.

### Status update
The server should send its current status to the API every minute.

Collect data of:

- Number of current players
- Number of maximum players
- Map

Send it to the API:

> `PATCH /server/<id>; { users_max: ..., users_current: ..., map: ..., is_alive: true }`

With a version coming soon, also data about online players should be sent. This can be prepared.

### Extra config
In the `extra` attribute (dict) of a server, additional config options can be supplied. This can vary by game.
For example there could be config parameters for reserved slots.


## User
### Registration
Every user playing on a server should be registered, if not already the case.

- On player connect, check if the user exists:

> `GET /user/<id>?type=<type>`, where `<id>` is the unique identifier of the `Player` at the authentication 
source `<type>` (e.g. the steam id for `STEAM`).

- If not, create user:

> `POST /user/; { identifier: <id>, type: <type> }`

- If the API doesn't return a valid response for the GET request (404 or 200), retry it every minute.

- On success, save the user object in a dictionary `[Player ID] -> [VyHub user object]`. 
If possible, save the `id` of the VyHub user in the `Player` object.

### Get user data
Create a function that returns the VyHub user for a `Player` ID. 
The function should only query the API if the user does not exist in the user dictionary.

### Sync groups
On player connect and every few (5) minutes, the groups of a player should be synced.

- Get the active groups of a user in the serverbundle:

> `GET /user/<id>/group?serverbundle_id=<serverbundle_id>`

- If the game only supports one group per user, select the group with the highest permission level.

- Of all groups that should be synced, get the corresponding in-game group name(s) from `group.mappings.name`.
Get all group names of mappings that have the same serverbundle id as the current server. There may be multiple mappings per group for the same serverbundle if multigroup is supported.

- Check all current groups of the player. Remove all groups that the player should not have and add all groups
that the player doesn't have yet. It may be required to check which permissions/group system a server uses.

- Notify the player about the changes.

### Capture in-game group changes
If the group of a player gets changed in game by an admin, this change should also be reflected in VyHub.

As this procedure isn't trivial, it can be skipped and done later, as it is not crucial for a successful operation.

For this, we need to

- Fetch all groups

> `GET /group`

- Create a mapping from `Game group name` -> `VyHub Group`. How the game group name is retrieved is explained in the 
`Sync groups` chapter (use `group.mappings`).

- With this prerequisite, we can not create a function that sets the group of a user.
The function should take the player id, group name, length of membership and processor id as parameters.
In this function, we create a new membership with the API:

> `POST /user/<id>/membership[?morph_user_id=<processor_id>]; { begin: <current timestamp>, end: <end timestamp>,  group_id: ..., serverbundle_id: ...}`
, where `<id>` is the id of the user that should become member of the group
and `<processor_id>` the id of the user that initiated the group change. If the processor is unknown, the `morph_user_id` can be omitted.
! In this case, a permission check must be done on the server !

The group id can be found by looking up the group name parameter in the group mapping that was created in step 2.

- Listen to group changes on the server (by registering event  listeners or intercepting functions) and call the according function.

- If the group system of the game is capable of multiple groups at once, group membership must also be terminated when the group is
removed from the player. There are two ways for this:

> `DELETE /user/<id>/membership?serverbundle_id=<serverbundle_id>[&morph_user_id=<processor_id>]`: 
Terminate all memberships of the user in the serverbundle.

Or

> `GET /user/<id>/membership?serverbundle_id=<serverbundle_id>`: get all memberships of a user, find the correct one and
terminate it with `DELETE /user/membership/<membership_id>[?morph_user_id=<processor_id>]`.

## Bans
Bans are important for a gameserver. Therefore, the most important functions must always work, even if the API is unreachable.

### Receive bans and enforce them
There should be a function that fetches the ban list from the API.

- Fetch active bans for the serverbundle:

> `GET /server/bundle/<serverbundle_id>/ban?active=true`

- Save the result for the runtime and in the cache. If the API isn't available on server start, load the bans from the cache.

This function should be called on server start (`vyhub_ready`), after player bans/unbans and once a minute.

- After refreshing the ban list: For all players on the server, check if their unique id is present in the ban list (as a key of the dict).
If yes, kick them from the server. There should be a separate function to check if a player is banned, because more
possible ways for a player to be counted as banned will be introduced below.

- Add a hook on player login/connect/auth that checks if the player is on the ban list. If yes, kick the player with the provided ban message.

### Banning/Unbanning a player
There must be a function that adds a ban for a player and a function that unbans the player.

To archive this, two queues should be introduced: A queue for bans and a queue for unbans.
Every change on one of the queues must be directly written to disk, to prevent data loss.
On server start, the last queue state should be read from disk.

#### Ban queue
Could be structured like this:

```
ban_queue: Dict[<player_id>,List[Dict[...]]]
    player_id: str
    length: int (seconds)
    reason: str
    creator_id: str
    created_on: date
    status: str
```

This allows a quick lookup, if a player is banned.

When creating a ban, it should be written into the ban queue, which is then saved in a file or similar.

Another function then processes the bans (regularly) in the ban queue and tries to send them to the API.
If 200 (ban created) or 404 (user not found) is returned by the API, the ban can be removed from the queue.
Else, the ban remains in the queue and will be retried f.e. every minute.
The creator of the ban should be informed about the outcome of the ban procedure.

Bans can be issued as follows:

> `POST /ban/[?morph_user_id=<processor_id>]; { user_id: ..., serverbundle_id: ..., length: ..., reason: ..., created_on: ..., status: ... }`, where `<processor_id>` is the id of the user that issued the ban. 
Omit the `morph_user_id` parameter if the ban has been issued by the server console.
! In this case, a permission check must be done on the server !

#### Unban queue
The unban queue is very similar to the ban queue, but can be structured less complicated:

```
unban_queue: Dict[<player_id>, <processor_id>]
```
Where `<processor_id>` is the id of the player that issued the unban.

When unbanning a player (id), the status of all bans in the ban queue for this player should be set to `UNBANNED`.
Additionally, an entry in the unban queue should be created.

Unbans can be issued as follows and can be removed from the queue afterwards:

> `PATCH /user/<id>/ban[?morph_user_id=<processor_id>]`, where `<id>` is the id of the user that should be unbanned and 
`<processor_id>` the id of the user that issued the unban. When no player (but for example the server console) issued

the unban, the `morph_user_id` parameter should be omitted.
! In this case, a permission check must be done on the server !

### Commands
There should be commands like `/ban <user> <length> <reason>` and `/unban <user>`.

If these commands already exist, they should be intercepted and the default operation should be suppressed.

## Warnings
Warnings are easier to implement, as they don't need to be cached.

### Creating warnings
There should be a function to create a warning for a player. A warning can be created as follows:

> `POST /warning[?morph_user_id=<processor_id>]; { user_id: ..., serverbundle_id: ..., reason: ... }`

After creating a warning, the ban list should be refreshed.

### Commands
There should be a command like `/warn <user> <reason>`.

## Statistics
The online time of players should be counted and written to disk until sent to API.

To send the playtime to the API, we need to

- Get or create the user attribute definition:

> `GET /user/attribute/definition/playtime`

If the API is not available, use the cached definition. If the API returns a 404, create a new definition:

> `POST /user/attribute/definition; { name: "playtime", title: "Play Time", unit: "HOURS", type: "ACCUMULATED", accumulation_interval: "day", unspecific: true }`

- Cache this definition

- Send the playtime to the API. This should happen every 60 minutes and on server start.

> `POST /user/attribute/; { definition_id: ..., user_id: ..., serverbundle_id: ..., value: <playtime in hours> }`

- Reset the playtime counter to 0 after sending the playtime of a player.


## Rewards
WIP

## Messages and Translations
Whenever possible, messages should be sent to the involved players. All messages should be taken from an
exchangeable language file.
