# Discord Integration

> Read this [guide](../guide/authorization.md) first to enable Discord authorization.


## Setup

1. In VyHub open the add server dialog in the `Server` settings. 
2. Get your `guild_id` and enter it as the servers address 
    - In Discord, open the server settings, go to `Widget` and copy the guild id
    ![Discord Role Permissions](../assets/game_integration_guide/discord_roles.png)
3. Click the `Add Bot to Guild` link. 
    - If the link is not visible, create an [application](../guide/authorization.md) first
    - Format of link: `https://discord.com/api/oauth2/authorize?client_id={discord_application_id}&permissions=268438529&scope=bot`
4. Make sure the bot has the ability to change roles.
    - In Discord, open the server settings.
    - Go to `Roles` and drag and drop VyHub Bot above groups you want to have synced.
    ![Discord Guild Id](../assets/game_integration_guide/discord_guild_id.png)

    > For higher security do not allow the bot to sync admin groups.


## Group Sync
User groups are automatically synced.

VyHub group names can be mapped to in-game groups at the `Advanced Properties` tab in the group settings. Please pay attention to capitalization.

## Troubleshooting
__Problem:__ Roles are not synced with Discord.

__Solution:__ Make sure roles have the exact name as provided to VyHub (Capitalization / Whitespaces...) and that the VyHub role has higher permissions than other roles.
