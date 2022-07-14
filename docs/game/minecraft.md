# Minecraft

Since version 1.1.0, a Minecraft integration is available. Please note that the integration is new and issues may occur.

Download Link:
[https://github.com/matbyte-com/vyhub-minecraft/releases](https://github.com/matbyte-com/vyhub-minecraft/releases)

## Compatible Permission Mods

One of the following permission mods is required:

- [LuckPerms](https://luckperms.net)

## Installation

- WIP

## Group Sync
User groups are automatically synced. For this to work correctly, the serverbundle must be in `multigoup: enabled` mode.

VyHub group names can be mapped to in-game groups at the `Advanced Properties` tab in the group settings.


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

## Commands

- `/timeban <player> <minutes> <reason>`: Ban a player for the specified time.
- `/warn <player> <reason>`: Warn a player
- `/login <token>`: Login to the VyHub website with a given token