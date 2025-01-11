# Server / Serverbundle

Gameservers are organised within serverbundles for grouping and better management.

`Servers` within the same `serverbundle` are from the same type (e.g. GMod, Minecraft).

`Serverbundles` are an abstraction from `servers`.  
Other features of VyHub like [Bans](ban.md)/[Warnings](warning.md) and the [Shop](shop/general.md) are using
serverbundles.

## Attributes

### Serverbundle

| Attribute       | Description                                                                             |
|-----------------|-----------------------------------------------------------------------------------------|
| Multiple Groups | If enabled, a user can be member in multiple groups simultaneously                      |
| Default Group   | Default group every user (also non-logged-in users) has by default in the serverbundle. | 

### Server

| Attribute      | Description                                                                    |
|----------------|--------------------------------------------------------------------------------|
| Address        | Server address                                                                 |
| Port           | Port on which the service is running on                                        |
| Reserved Slots | Number of reserved slots (where only users with the required property can join |
| Serverbundle   | Serverbundle the server is assigned to                                         |

## Connect a new Gameserver

Navigate to the `Server` settings.  
Press the `Add Server` button and follow the steps in the dialog.

After you have added the server in your `VyHub instance` you need to install one of our plugins on your server.

## Server Dashboard

The server dashboard shows current server information like a list of online players.

It can be accessed through the server-status on the startpage (news) or directly through the url:

- `https://<frontend-url>/server-dashboard/<server-id>`: The dashboard of the server with the respective server id


