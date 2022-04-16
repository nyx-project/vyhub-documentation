# Discord Integration

## Setup

- Add a new server in the `server` settings.
- Enter your Discord `guild id` as `address` 
  - In Discord, open the server settings 
  - Go to `Widget` and copy the guild id
  ![Discord Guild Id](../assets/game_integration_guide/discord_guild_id.png)
  

- Make sure the bot has the ability to change all roles.
  - In Discord, open the server settings.
  - Go to `Roles` and drag and drop VyHub Bot above groups you want to have synced.
  ![Discord Role Permissions](../assets/game_integration_guide/discord_roles.png)

> For higher security do not allow the bot to sync admin groups.

## Group Sync
User groups are automatically synced.

VyHub group names can be mapped to in-game groups at the `Advanced Properties` tab in the group settings. Please pay attention to capitalization.

> Read this [guide](../guide/authorization.md) to enable Discord authorization.

## Troubleshooting
__Problem:__ Roles are not synced with Discord.

__Solution:__ Make sure roles have the exact name as provided to VyHub (Capitalization / Whitespaces...) and that the VyHub role has higher permissions than other roles.
