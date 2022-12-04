# Changelog

Ad
## v1.3.2
Released: 2022-12-04

Web/API:
- Fix problem where ban-protests could not be created

## v1.3.1
Released: 2022-11-26

Web/API:

- Fix problem with new navigation settings (making changes was not possible)
- Improve design of navigation settings

Garry's Mod:

- Add german translation
- Fix loading problem of in-game dashboard

Update notes:

- **Important:** Due to a problem with the latest update, the admin menu in the navigation is visible for all users. To fix this, go to the navigation settings, edit the admin menu entry and insert `admin_menu` as required property. ***This problem only occurs when the instance has been upgraded from 1.2.x to 1.3.0.***

## v1.3.0
Released: 2022-11-23

Web/API:

- Improve navigation settings by allowing to create sub-menus and by limiting access with requirement sets.
- Make it possible to add navigation links to footer and help-menu
- Fix icon picker

Garry's Mod:

- Add warning/ban dashboard for Garry's Mod (`!dashboard`)
- Make it possible to translate on [translate.matebyte.com](https://translate.matbyte.com/projects/vyhub/vyhub-gmod/). More parts will be translatable soon.
- Improve ban/warn messages

Update notes:

- If you have used custom navigation links in the past, they will be resetted to a default value.
    - Your custom HTML pages won't be lost, but they need to be linked again.
- The following game integrations need to be updated:
    - Garry's Mod -> v1.3.0

## v1.2.1
Released: 2022-10-22

- Improve packet images and titles
- Only display serverbundles on the home page that contain servers
- Fix error when importing GExtension statistics
- Fix paysafecard certificates

## v1.2.0
Released: 2022-10-09

- Add easier server setup process
- Add packet subcategories
- Add support for custom packet price
- Add option to include tax in packet price
- Add option to limit coupon usages by user
- Add option to accept pending stripe payments
- Add support for two packet relations: Disable, Upgrade
- Add option to execute reward again if the packet gets extended (e.g. by a subscription payment)
- Add string replacements for packet name and purchase amount
- Add support for client certificate auth for paysafecard API (experimental)
- Add option to download all invoices in a given timerange as ZIP
- Show how often a coupon has been used
- Fix problems with Mojang API
- Fix credit refund
- Small design improvements
- Several bugfixes

Update notes:

- The following game integrations should be updated:
    - Garry's Mod -> v1.2.0
    - Minecraft -> v1.2.0

## v1.1.4
Released: 2022-08-27

- Support stripe API version 2022-08-01
- Rework serverbundle tokens (introduce new `integration_token` property which contains all required properties)
- Hide customer address by default during checkout
- Improve better handling for unreachable steam API
- Improve error handling for Minecraft auth requests
- Fix refunding a purchase was not possible in some cases
- Improve french translations

Update notes:

- The following game integrations should be updated if not already the case:
    - Garry's Mod -> v1.1.5
    - Minecraft -> v1.1.3

## v1.1.3
Released: 2022-08-10

- Add ban protests
- Make it possible to set color for header and footer
- Make it possible to ban players by steamid in Garrys's Mod
- Finish [reserved slots](game/gmod.md#reserved-slots) in Garry's Mod

Update notes:

- The following game integrations need to be updated:
    - Garry's Mod

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
