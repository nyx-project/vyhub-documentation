# Teamspeak

VyHub allows you to monetize your Teamspeak server. It is possible to synchronize groups between VyHub and Teamspeak and
sell access to custom Teamspeak channels.

> Important: your Teamspeak server must support SSH connections. Telnet is not supported.

## Setup

1. Create a new TeamSpeak identity for the bot
    - In Teamspeak go to Tools -> Identities
    - Create a new identity. Give it a name and a nickname
2. Connect to your TeamSpeak server with the new identity
3. Give your bot identity the [necessary rights](#necessary-rights)
4. Create a ServerQuery login
    - Tools -> ServerQuery Login (if you can't click this button, you do not have enough permissions on your client)
    - Select a suitable name (do not use spaces or special character)
    - Click ok and copy the credentials
5. Add the following IP-addresses to the query whitelist of your teamspeak server. (`query_ip_allowlist.txt`)
    - 49.13.24.141
    - 168.119.53.171
6. In VyHub create a [serverbundle](../guide/server.md) of type Teamspeak
7. Create a [server](../guide/server.md)
    - Address: The address you use to connect to your Teamspeak server
    - Port: The port of the Teamspeak server (usually **9987**)
    - SSH Query Port: The ssh query port of the Teamspeak server (usually **10022**)
        - Note: your hoster may use a different port. Check with them!
    - Use the generated credentials as username and password
8. Restart your Teamspeak Server

## Debug: Show Query Clients

Teamspeak QueryClients are not shown by default. This is important to check whether the VyHub bot is connected to your
server.

1. Add your server as **bookmark**, edit the bookmark and enable the "Show ServerQuery Clients" option.

Now you should be able to see the connected ServerQuery clients.

![Discord Role Permissions](../assets/game_integration_guide/teamspeak_edit_bookmark.png)

## Group Sync

User groups are automatically synced.

VyHub group names can be mapped to server/in-game groups at the `Mappings` tab in the [group](../guide/group/group.md)
settings. Please pay attention to capitalization.

> It is possible to use "teamspeak group names" or "teamspeak group id's" in the `mappings`

## Necessary Rights

These rights are necessary for running the bot.

- `b_client_create_modify_serverquery_login`
- `b_virtualserver_notify_register`
- `b_client_server_textmessage_send`
- `b_client_channel_textmessage_send`
- `i_client_private_textmessage_power`
- `b_virtualserver_info_view`
- `b_virtualserver_client_list`
- `i_channel_subscribe_power` - only clients in subscribable channels are counted
- `i_channel_needed_subscribe_power` - only clients in subscribable channels are counted
- `b_virtualserver_servergroup_list`
- `i_group_member_add_power` - only clients with lower permission than bot are targetable
- `i_group_needed_member_add_power` - only clients with lower permission than bot are targetable
- `i_group_member_remove_power` - only clients with lower permission than bot are targetable
- `i_group_needed_member_remove_power`- only clients with lower permission than bot are targetable
- `b_virtualserver_client_dbinfo`
