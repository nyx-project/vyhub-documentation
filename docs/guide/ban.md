# Bans

Bans are targeting a user in one specific **[serverbundle](server.md)**. Bans across all serverbundles are also possible, by leaving the serverbundle field blank.

## Attributes

| Attribute    | Description                                                         |
|--------------|---------------------------------------------------------------------|
| Length       | [Optional] Length of the ban (empty for lifetime ban)               |
| Serverbundle | [Optional] Serverbundle the ban is targeting (empty for global ban) |

## Add / Edit

Bans can be added and edited through the designated `Bans` page.

## Ban Settings

You can find further ban configurations in the settings.

| Attribute       | Description                                   |
|-----------------|-----------------------------------------------|
| Ban Protest URL | [Optional] Target URL when user protest a ban |


## Protests

Users can create ban protests for active bans. By default, Ban protests are shown as a ticket. There can only be one open protest and a maximum of three total protests per ban.   
You can set a `Ban Protest URL` in the settings. Instead of creating a ticket, users are redirected to this site.

The button is disabled, when the `Ticket-System` is disabled and when there is no `Protest-Ban` URL set.

## Max ban length

You can assign a maximum ban length to groups. A user can then only create bans of the length the `maximum ban length` property of the group with the highest permission level.

## Website Bans

Players can be banned from your VyHub website as well. Just add them to the `Banned (Website)` group.
The group prevents users from using the shop, creating tickets and posting in the forum. The 3 relevant negative
properties are `shop_use`, `ticket_create`, `forum_post`.


