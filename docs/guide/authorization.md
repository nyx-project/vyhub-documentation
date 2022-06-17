# Authorization

The login at your VyHub instance is possible with multiple authentification providers.

## Central

Connect your account with `VyHub Central` to have another way of logging in or the ability of creating your own instances.

## Steam

Connect your account with `Steam` when playing Garry's Mod.

## Discord

Connect your account with `Discord` to enjoy the synchronization of groups between Discord and VyHub.

### Setup

1. In your VyHub instance go to the `Authorization` settings and enable Discord.
2. Go to the [Discord Developer Portal](https://discord.com/developers/applications) and create a new application.
3. Get your `client_id` and `client_secret`.
4. Enter the redirect URL shown in the `Authorization` settings.
![Discord Developer Settings](../assets/authorization_guide/discord_developer_portal.png)
5. Get your `bot_token` and enable the `presence` and `members` intent.
![Discord Bot Settings](../assets/authorization_guide/discord_bot_settings.png)


> Read this [guide](../game/discord.md) to add the Discord bot to your Discord guild.
