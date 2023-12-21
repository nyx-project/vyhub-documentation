# 7 Days To Die

Download the newest `VyHub.cs` here:
[https://github.com/matbyte-com/vyhub-umod/releases](https://github.com/matbyte-com/vyhub-umod/releases)

## Compatible 7 Days to Die Plugin APIs / Mods

- Umod / Oxide

## Installation


1. In VyHub open the `Add Server` dialog in the `Server` settings and create the server.
2. Click on the `Setup` button of the server and follow the instructions.
3. Optionally, adjust the config files to your needs.


## Group Sync

User groups are automatically synced. For this to work correctly, the [serverbundle](../guide/serverbundle.md) must be in `multigoup: enabled` mode.

VyHub group names can be mapped to in-game groups at the `Advanced Properties` tab in the [group](../guide/group.md) settings.


## Bans and Warnings

> Bans and Warnings are synced between servers within one serverbundle.


## Rewards
For Rust, the following types of rewards are supported:

- `COMMAND`: Executes a console command on the server

> Do not rely on `onSpawn` event. It is not triggered correctly. Unfortunately, we can not do anything about it as it directly depends on UMOD.

### Available replacements
The following string replacements are available for rewards:

- `%user_id%`: The VyHub user id
- `%nick%`: The players in-game nickname
- `%applied_packet_id%`: The id of the applied packet
- `%steamid64%`: The players steam id
- `%packet_title%`: The title of the packet
- `%purchase_amount%`: Total amount with currency of the purchase. For example `30 EUR`. If packet was applied without purchase: `-`.

## Commands

- `/warn <player> <reason>`: Warn a player
- `/vh_config <key> <value>`: Set a config option
- `/vh_setup <api-key> <api_url> <server_id>`
