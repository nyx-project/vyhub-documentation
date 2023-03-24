# Discord

VyHub allows you to monetize your Discord server. It is possible to sync groups between VyHub and Discord.

> Read this [guide](../guide/authorization.md) first to enable Discord authorization.


## Setup

1. In VyHub open the `Add Server` dialog in the `Server` settings. 
2. Get your `Guild ID` and enter it as the servers address 
    - In Discord, open the server settings, go to `Widget` and copy the guild id
    ![Discord Role Permissions](../assets/game_integration_guide/discord_guild_id.png)
3. Create the server
4. Click on the `Setup` button of the server.
3. Click on the `Add` button to add the Bot to your Discord server. 
    - If the button is not working, create an [application](../guide/authorization.md) first
    - The link can also be created manually: `https://discord.com/api/oauth2/authorize?client_id={discord_application_id}&permissions=268438545&scope=bot`
4. Make sure the bot has the ability to change roles.
    - In Discord, open the server settings.
    - Go to `Roles` and drag and drop VyHub Bot above groups you want to have synced.
    ![Discord Guild Id](../assets/game_integration_guide/discord_roles.png)

    > For higher security do not allow the bot to sync admin groups.


## Group Sync
User groups are automatically synced.

VyHub group names can be mapped to server/in-game groups at the `Mappings` tab in the [group](../guide/group.md) settings. Please pay attention to capitalization.  

> It is possible to use "role names" or "role ids" in the `mappings` 

## Troubleshooting
__Problem:__ Roles are not synced with Discord.

__Solution:__ Make sure roles have the exact name as provided to VyHub (Capitalization / Whitespaces...) and that the VyHub role has higher permissions than other roles.
Also have a look in the logs, the Discord errors might help, when the bot can't connect to the Discord API.
