# Garry's Mod

Download Link:
[https://github.com/matbyte-com/vyhub-gmod/releases](https://github.com/matbyte-com/vyhub-gmod/releases)

## Compatible Admin Mods

- xAdmin (1/2)
- ULX
- ServerGuard
- SAM
- FAdmin
- Maybe more

## Installation

- Clone the repo into your `addons/` folder. Alternatively, download the ZIP archive from GitHub. 
- Rename `lua/vyhub/config/sv_config.lua.example` to `sv_config.lua`
- Edit `lua/vyhub/config/sv_config.lua`:
    - Set `VyHub.Config.api_url` to your API URL. You can find the URL at the instance details on [https://vyhub.net](https://vyhub.net/dashboard).
    - Set `VyHub.Config.api_key` to the serverbundle API key you can get at `Admin` -> `Settings` -> `Servers` -> `Serverbundle`.
    - Set `VyHub.Config.server_id` to the ID of the gamserver this addon is installed. It can also be found at `Admin` -> `Settings` -> `Servers`.
- Adjust the other settings to your needs.

## Group Sync
User groups are automatically synced. For this to work correctly, the serverbundle must be in `multigoup: disabled` mode.

VyHub group names can be mapped to in-game groups at the `Advanced Properties` tab in the group settings.


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

For the `SCRIPT` reward, the player object is available in the script as `PLAYER`.

## Commands

- `!dashboard`: Open server dashboard
- `!warn <user> <reason>`: Warn a user

## Lua

- `ply:VyHubID()`: Return VyHub user ID. May be `nil`.
- `VyHub.API:{get,post,patch,delete}(...)`: Use VyHub API

## Troubleshooting

### Broken Bans/Unbans

__Problem:__ Every few seconds the server tries to send a ban to VyHub, but the ban data is malformed, which causes the request to never succeed.

__Solution:__ Delete the file `data/vyhub/ban_queue.json`.