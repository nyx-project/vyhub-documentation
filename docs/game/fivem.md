# FiveM
Download `vyhub-fivem-?.?.?.zip` fitting to your version here:

[https://github.com/matbyte-com/vyhub-fivem/releases](https://github.com/matbyte-com/vyhub-fivem/releases)


## Compatible Mods

- ESX

## Installation

1. In VyHub open the `Add Server` dialog in the `Server` settings and create the server.
2. Click on the `Setup` button of the server and follow the instructions.
3. Optionally, adjust the config files to your needs.

## Group Sync
User groups are automatically synced. For this to work correctly, the serverbundle must be in `multigoup: disabled` mode.

VyHub group names can be mapped to in-game groups at the `Advanced Properties` tab in the group settings.

The group sync can be disabled in `sv_config.lua`.

## Commands

- `/dashboard`: Open server dashboard (with bans and warnings)

* Commands are configurable in `config/sv_config.lua`

## Rewards
For FiveM, two types of rewards are supported:

- `COMMAND`: Executes a console command on the server
- `SCRIPT`: Executes a Lua script on the server

### Available replacements
The following string replacements are available for both types of rewards:

- `%id%`: The players server/source id
- `%user_id%`: The VyHub user id
- `%esx_name%`: The players in-game ESX character name
- `%nick%`: The players FiveM nickname
- `%license%`: The players Rockstar GTA license
- `%steam_id%`: The players steamid
- `%applied_packet_id%`: The id of the applied packet
- `%packet_title%`: The title of the packet
- `%purchase_amount%`: Total amount with currency of the purchase. For example `30 EUR`. If packet was applied without purchase: `-`.

## Dashboard, Bans & Warnings
The dashboard can be opened with the `dashboard` command.

On the dashboard, bans and warnings can be seen, edited and created.

## Lua

- `VyHub.API:{get,post,patch,delete}(...)`: Use VyHub API


## Console Commands

The console commands can only be used in the server console.

- `vh_ban <license> <minutes> <reason>`: Ban a player
- `vh_unban <license>`: Unban a player
- `vh_warn <license> <reason>>`: Warn a player


## Troubleshooting

### Broken Bans/Unbans

__Problem:__ Every few seconds the server tries to send a ban to VyHub, but the ban data is malformed, which causes the request to never succeed.

__Solution:__ Delete the file `data/ban_queue.json`.
