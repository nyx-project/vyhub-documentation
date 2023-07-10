# Minecraft

Since version 1.1.0, a Minecraft integration is available. Please note that the integration is new and issues may occur.

Download Link:
[https://github.com/matbyte-com/vyhub-minecraft/releases](https://github.com/matbyte-com/vyhub-minecraft/releases)

## Compatible Minecraft Plugin APIs

- Bukkit/Spigot/Paper (>=1.12)

## Compatible Permission Mods

One of the following permission mods is required to enable the group-sync between VyHub and Minecraft:

- [LuckPerms](https://luckperms.net)

## Installation

1. In VyHub open the `Add Server` dialog in the `Server` settings and create the server.
2. Click on the `Setup` button of the server and follow the instructions.
3. Optionally, adjust the config files to your needs.

## Group Sync

> Group-Sync is deactivated when no permission-mod is found

User groups are automatically synced. For this to work correctly, the [serverbundle](../guide/serverbundle.md) must be in `multigoup: enabled` mode.

VyHub group names can be mapped to in-game groups at the `Advanced Properties` tab in the [group](../guide/group.md) settings.


## Rewards
For Minecraft, the following types of rewards are supported:

- `COMMAND`: Executes a console command on the server

### Available replacements
The following string replacements are available for rewards:

- `%user_id%`: The VyHub user id
- `%nick%`: The players in-game nickname
- `%player_id%`: The players minecraft UUID
- `%player_ip_address%`: The players IP address
- `%applied_packet_id%`: The id of the applied packet
- `%packet_title%`: The title of the packet
- `%purchase_amount%`: Total amount with currency of the purchase. For example `30 EUR`. If packet was applied without purchase: `-`.

## Commands

- `/timeban <player> <minutes> <reason>`: Ban a player for the specified time.
- `/warn <player> <reason>`: Warn a player
- `/login <token>`: Login to the VyHub website with a given token
- `/vh_config <key> <value>`: Set a config option
- `/vh_setup <api-key> <api_url> <server_id>`
