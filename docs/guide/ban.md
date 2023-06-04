# Bans

Bans are targeting a user in one specific **[serverbundle](server.md)**. Bans across all serverbundles are also possible, by leaving the serverbundle field blank.

## Attributes

| Attribute    | Description                                                         |
|--------------|---------------------------------------------------------------------|
| User         | Targeted user                                                       |
| Reason       | Reason for the ban                                                  |
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
