# Changelog

## v1.1.2
Released: 2022-07-31

- Fix coupon payment requests cannot be deleted

## v1.1.1
Released: 2022-07-26

- Fix credit history view of other users
- Improve first start guide
- Smaller bugfixes

## v1.1.0
Released: 2022-07-19

- Add [minecraft](game/minecraft.md) integration
- Add [adverts](guide/adverts.md)
- Add URL to get to a users dashboard by its in-game id, see [user](guide/user.md).
- Allow deletion of payment gateways, packets and purchases
- Add server details dialog
- Fix notification mails
- Fix problem with pending PayPal payments
- Make it possible to format packet descriptions
- Several bugfixes

Update notes:

- The following game integrations need to be updated:
    - Garry's Mod
- Serverbundle API keys need to be regenerated


## v1.0.0
Released: 2022-06-17

- Add server dashboard (current online users)
- Add FAQ system
- Add last online for users
- Add ability for manually adding credits to users and see credit history
- Add support for free packets
- Add support for PayPal subscriptions
- Make it possible to add multiple memberships at once (for multiple bundles)
- Improve property picker
- Improve error messages
- Improve redirect after login
- Smaller fixes

Update notes:

- If you used PayPal in the past, you need to add the webhook id in the settings. Follow the [guide](guide/shop/payment_gateway.md).
- The following game integrations need an update:
    - Garry's Mod

## v0.4.3-beta
Released: 2022-05-04

- Group mappings can no be created without a serverbundle (mapping is then valid for all bundles)
- Fix discord bot creating too much invitations
- Update translations
- Smaller fixes

Update notes:

- The permissions of the Discord bot changed. Either remove and re-add the bot to your server or add the "Manage channels" permission to the bot role.

## v0.4.2-beta
Released: 2022-04-25

- Add new group mapping feature
- Prepare Minecraft support (the Minecraft integration has not been released yet!)
- Improve user data sync
- Readd Discord integration. Please read the [docs](game/discord.md)
- Improve rate limiting (higher limits for server API tokens)
- Add support for other languages (added French, German, Spanish)
- Further bugfixes

Update notes:

- Group mappings have to be recreated. There is no automatic migration from the old `server_group`.
- The following game integrations need an update:
    - Garry's Mod

## v0.4.1beta
Released: 2022-04-17

- Add Discord integration (login, group sync and server status)
- Add option to set default currency
- New instances now get a random theme
- Fix purchase cancelling always causes a notification
- Fix PayPal not working in production mode
- Fix cancelling stripe payments not working
- Fix error when having packets with different currencies in the cart
- Fix external links not working on mobile
- Bugfixes

The following game integrations need an update:

- Garry's Mod

## v0.3.2beta
Released: 2022-03-14

- Add E-Mail notifications
- Fix linking accounts not working sometimes
- Bugfixes

## v0.3.1beta
Released: 2022-03-06

- Bugfixes

## v0.3.0beta
Released: 2022-03-05

- Add coupon payment gateway
- Add ability to see/edit/delete applied rewards
- Improve tickets overview
- Improve performance
- Restructure shop
- Several bugfixes
