# Bans and Warnings

Bans and Warnings are another cool feature of VyHub. They make sure you are able to enforce rules on your server and
make it also more transparent for the players. Your player can always see their current warnings and bans on your VyHub
instance. There they are, for example, also able to protest a ban.

## Warnings

Warnings are a way to let users know that they did something wrong, without banning them.
You can configure in the settings, after how many warning a ban gets issued.

You can also integrate the Warning System with other plugins that automatically issue warnings.

### Attributes

| Attribute    | Description                                                             |
|--------------|-------------------------------------------------------------------------|
| Serverbundle | Serverbundle the warning is targeting and where the ban is then created |

### Add / Edit

Warnings can be added and edited through the designated `warning` page.

### Warning Settings

You can find further warning configurations in the settings.

| Attribute                             | Description                                                                                   |
|---------------------------------------|-----------------------------------------------------------------------------------------------|
| Warning Time To Live                  | How many days a warning is considered as `active`                                             |
| Number of warning till automatic bans | How many `active` warnings it requires for a user to get banned (0 to disable automatic bans) |
| Length of automatic ban               | How long (minutes) a user will be banned if the warning threshold has been reached            |

## Bans

Bans are targeting a user in one specific **[serverbundle](server.md)**. Global Bans across all serverbundles are also
possible, by leaving the serverbundle field blank.

### Attributes

| Attribute    | Description                                                         |
|--------------|---------------------------------------------------------------------|
| Length       | [Optional] Length of the ban (empty for lifetime ban)               |
| Serverbundle | [Optional] Serverbundle the ban is targeting (empty for global ban) |

### Add / Edit

Bans can be added and edited through the designated `Bans` page.

### Ban Settings

You can find further ban configurations in the settings.

| Attribute       | Description                                   |
|-----------------|-----------------------------------------------|
| Ban Protest URL | [Optional] Target URL when user protest a ban |

### Protests

Users can create ban protests for active bans. By default, Ban protests are shown as a ticket. There can only be one
open protest and a maximum of three total protests per ban.   
You can set a `Ban Protest URL` in the settings. Instead of creating a ticket, users are redirected to this site.

The button is disabled, when the `Ticket-System` is disabled and when there is no `Protest-Ban` URL set.

### Max ban length

You can assign a maximum ban length to groups. A user can then only create bans of the length the `maximum ban length`
property of the group with the highest permission level.

### Website Bans

Players can be banned from your VyHub website as well. Just add them to the `Banned (Website)` group.
The group prevents users from using the shop, creating tickets and posting in the forum. The 3 relevant negative
properties are `shop_use`, `ticket_create`, `forum_post`.


