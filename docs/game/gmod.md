# Garry's Mod

Download `vyhub-gmod-?.?.?.zip` fitting to your version here:

[https://github.com/matbyte-com/vyhub-gmod/releases](https://github.com/matbyte-com/vyhub-gmod/releases)


## Compatible Admin Mods

- xAdmin (1/2)
- ULX
- ServerGuard
- SAM
- FAdmin
- Maybe more

## Installation

1. In VyHub open the `Add Server` dialog in the `Server` settings and create the server.
2. Click on the `Setup` button of the server and follow the instructions.
3. Optionally, adjust the config files to your needs.

## Group Sync
User groups are automatically synced. For this to work correctly, the serverbundle must be in `multigoup: disabled` mode.

VyHub group names can be mapped to in-game groups at the `Advanced Properties` tab in the group settings.

## Commands

- `!dashboard`: Open server dashboard (with bans and warnings)
- `!warn <user> <reason>`: Warn a user

## Rewards
For Garry's Mod, two types of rewards are supported:

- `COMMAND`: Executes a console command on the server
- `SCRIPT`: Executeds a Lua script on the server

### Available replacements
The following string replacements are available for both types of rewards:

- `%user_id%`: The VyHub user id
- `%nick%`: The players in-game nickname
- `%steamid64%`: The players steamid64
- `%steamid32%`: The players steamid32
- `%uniqueid%`: The players uniqueid
- `%applied_packet_id%`: The id of the applied packet
- `%packet_title%`: The title of the packet
- `%purchase_amount%`: Total amount with currency of the purchase. For example `30 EUR`. If packet was applied without purchase: `-`.

For the `SCRIPT` reward, the player object is available in the script as `PLAYER`.


## Reserved Slots
It is possible to configure reserved slots in the server settings.

| Setting    | Description                                              |
|--------------|----------------------------------------------------------|
| Number of reserved slots         | How many slots of the total slots of your server should be reserved.  |
| Keep reserved slots free       | If this is enabled, the reserved slots will not actually be used. Instead, a player with access to a reserved slot will automatically kick the newest player if the server is full. However, for this to work, a few of these fake reserved slots must exist to allow permitted players to join even if the server is full. |
| Hide reserved slots       | Hide the reserved slots in the server browser. Only the slot count without the reserved slots will be shown. This works best together with the "Keep reserved slots free" option. |

### Giving access to reserved slots
There are two ways to give a player access to reserved slots:

1. By adding the user to a group that has the `reserved_slot_use` property.
2. By creating a reward on connect that executes the following script:

    `table.insert(VyHub.Server.reserved_slot_plys, PLAYER:SteamID64())`


## Lua

- `ply:VyHubID()`: Returns VyHub user ID. May be `nil`.
- `VyHub.API:{get,post,patch,delete}(...)`: Use VyHub API


## Console Commands

The console commands can only be used in the server console.

- `vh_dashboard`: Open/Close server dashboard
- `vh_reinit`: Reinitialize VyHub addons
- `vh_ban <steamid64> <minutes> <reason>`: Ban a player
- `vh_unban <steamid64>`: Unban a player
- `vh_setgroup <steamid64> <group> [<bundle>]`: Add player to a group in a serverbundle. By default the serverbundle of the executing server is used.


## Troubleshooting

### Broken Bans/Unbans

__Problem:__ Every few seconds the server tries to send a ban to VyHub, but the ban data is malformed, which causes the request to never succeed.

__Solution:__ Delete the file `data/vyhub/ban_queue.json`.