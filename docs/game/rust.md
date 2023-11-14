# Rust

Download Link:
[https://github.com/matbyte-com/vyhub-umod/releases](https://github.com/matbyte-com/vyhub-minecraft/releases)

## Compatible Rust Plugin APIs / Mods

- Umod / Oxide
- Carbon

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
- `/dashboard`: Opens the Rust VyHub dashboard (when the correct permissions are set)
- `/vh_config <key> <value>`: Set a config option
- `/vh_setup <api-key> <api_url> <server_id>`

## Permissions

To use the VyHub dashboard, the player needs to have the corresponding permissions

- `"vyhub.dashboard"`
- `"vyhub.warn"`
- `"vyhub.ban"`
- `"vyhub.unban"`
