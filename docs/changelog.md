# Changelog

## v1.5.10  

Released: 2023-07-17  

- [WEB] Raise max HTML character length
- [WEB|API] Add HTTP-Rewards

## v1.5.9  

Released: 2023-07-16

- [WEB] Fix edit forum post

Released 2023-07-13

Minecraft (v1.5.1)

- Fix creation of config-file after startup
- Add BungeeCord support
- Add Velocity support

## v1.5.8  

Released: 2023-07-10

- [WEB|API] Support for custom CSS
- [WEB] Improve team-page when avatar is not found

Minecraft (v1.5.0):

- Add support for Bukkit/Spigot/Paper versions from 1.12+ with Java 8+
- Remove strict LuckPerms requirement (Only disable group-sync, when LuckPerms is not found)
- Add internationalization

## v1.5.7

Released: 2023-07-05

- [WEB|API] Add option to prohibit users from creating threads in topics
- [WEB|API] Threads without posts are now displayed in frontend as well
- [API] Fix creation of bans with game-plugins under some circumstances

## v1.5.6

Released: 2023-07-04

- [WEB] Fix forum thread view when logged in under some circumstances
- [API|WEB] Add requirement set tester to test requirements sets against users
- [API] Improve handling of requirement sets when no formula or wrong formula is set

## v1.5.5

Released: 2023-06-25

Web/API:

- [API] Change default currency to EUR
- [API] Disable "all packets" option when creating a discount with packets specified
- [API] Fix GExtension group import
- [API] Improve E-Mail template
- [API] Various performance improvements
- [API|WEB] Add option to unlink accounts (for admins)
- [API|WEB] Add option to add Google Analytics tag
- [API|WEB] Fix problems with theme colors
- [Web] Add beginner guide
- [Web] Fix group form
- [Web] Fix user/ban comment spacing
- [Web] Fix forum thread view when not logged in
- [Web] Improve mobile view of home/news page
- [Web] Improve mobile view of log page
- [Web] Improve server dashboard
- [Web] Improve "no data" message
- [Web] Improve link user dialog

Garry's Mod (v1.5.1):

- Performance improvements
- Add options to limit execution of reward scripts/commands
- Add options to disable ban/group sync

Update notes:

- vyhub-gmod v1.5.1 disables the execution of Lua script rewards by default. Script execution can be enabled in the `sv_config.lua` or by executing this command in the server console: `vh_config reward_disable_scripts false`
    - Script execution will be kept enabled if `sv_config.lua` is not replaced during update 

## v1.5.4

Released: 2023-06-14

Web/API:

- [API] Discord: Remove bot started log message
- [API] Discord: Improve error handling
- [API] Sync Discord/Ts3 groups on first login
- [WEB] Discord: Add button to restart bot
- [WEB] Fix button to edit a users credits was not visible
- [WEB] Fix ban details could not be seen when not logged in
- [WEB] Improve mobile view of new users


## v1.5.3

Released: 2023-06-10

Web/API:

- [API] Fix creation of bans under some circumstances
- [WEB] Show groups on user dashboard at all time

## v1.5.2

Released: 2023-06-09

Web/API:

- [API|WEB] Add `maximum ban length` property to groups  
- [WEB] Add in-game purchase notification to reward templates

Discord:

- Add chat notifications. All settings regarding the chat notification are done through Discord by interacting with the bot.

## v1.5.1

Released: 2023-06-05

Web/API:

- [API] Fix creation of groups
- [WEB] Fix select all property btn on group creation

## v1.5.0

Released: 2023-06-04

Web/API:

- [API|WEB] Rework Logs. Logs are now saved on a dedicated logging-server and are better tagged.
- [API|WEB] Add user and ban comments
- [API|WEB] Add further and improve existing shop statistics
- [WEB] Add reward presets. Presets can be used out of the box are may inspire your own rewards.
- [WEB] Improve FAQ design

Teamspeak Integration:

- Use additional ssh query port field for connection to server.
- Use existing port to create the connection link on the homepage.

Update notes:

- Due to the restructuring of the logs, old logs are not available in the UI. Old logs can be downloaded at the bottom of the logs page.

## v1.4.6

Released: 2023-05-12

Web/API:

- [API|WEB] Add ability to add rewards to already applied packets.
- [WEB] Add embed video functionality to editor (only for admins)
- [WEB] Fix field to remove image-url of packets

## v1.4.5

Released: 2023-05-07

Web/API:

- [API] Improve performance of ban and warn endpoints
- [WEB] Fix removing of nav icons not working
- [WEB] Fix open graph tags for high available instances

## v1.4.4

Released: 2023-05-06

Web/API:

- [WEB] Add ability to specify external ban-protest URL
- [WEB] Shop: Add option to show packet title over packet image
- [API] Add `GET /ban/{uuid}` endpoint
- [API] Add `GET /warning/{uuid}` endpoint
- [API] Fix user attribute history missing entries for days without value in some cases
- [API] Fix missing translations for invoices
- [API|WEB] Make serverbundles sortable
- [API|WEB] Update translations

## v1.4.3

Released: 2023-05-02

Web/API:

- [API] Fix number of top-donators returned by API
- [WEB] Add ability to specify number of top-donators for widget
- [WEB] Add ability to search for users using SteamID32
- [WEB] Add ability to set open graph tags for instance

Update notes:
  - There is no migration for your community description and favicon
    - Please set them to your desired values in the settings manually.

## v1.4.2

Released: 2023-04-24

Web/API:

- [API] Fix notification mails
- [WEB] Add top-donator widget
- [WEB] Add ability to specify custom text for donation goal and top-donator widgets
- [WEB] Improve responsiveness of header

Garry's Mod:

- [Server] Improve HTTP error messages

Minecraft: 

- [Server] Fix error for new players and on VyHub user creation

Update notes:

- The following game integrations can be updated:
    - Garry's Mod -> v1.4.2
    - Minecraft -> v1.4.1

## v1.4.1

Released: 2023-04-09

Web/API:

- [API] Forum: Fix post count
- [API] Fix error when trying to delete a serverbundle with existing warnings
- [API] Fix team page

Garry's Mod:

- [Client] Fix server dashboard icons
- [Server] Fix error for new players and on VyHub user creation
- [Server] Smaller improvements

Update notes:

- The following game integrations can be updated:
    - Garry's Mod -> v1.4.1

## v1.4.0

Released: 2023-04-05

Central:

- VyHub instances are now free to use, [but paid with a small revenue commission](central/account.md) 
- Add VyHub Balance panel
- Add Affiliate panel

Web/API:

- [API] Add `DELETE /user/{uuid}/membership/by-group` endpoint: Remove a group membership of a user by using a group id
- [API] Improve search for log entries
- [API|Web] Add new add-on: [Forum](guide/forum.md) 
- [API|Web] Add Teamspeak integration
- [API|Web] Add translated invoices
- [API|Web] Add option to buy packets for other users
- [API|Web] Improve reordering of shop packets
- [API|Web] Discord: Add option to use role-ids in group mappings
- [Web] Add option to duplicate packets
- [Web] Add discount code generator
- [Web] Add option to select all properties when creating / editing groups
- [Web] Add pagination for the payments of a purchase
- [Web] Add secondary color
- [Web] Improve table colors for bans, warnings, tickets and on the server dashboards


Update notes:

- **Important:** Our terms of service have changed to reflect the changes in the pricing of instances. Therefore, the next time you extend your instance, you need to agree to our new terms of service and privacy policy.

## v1.3.4

Released: 2022-12-29

Web/API:

- Fix invoice generation not working sometimes
- Fix navigation sublinks sometimes not deletable
- Stripe: Add more payment gateways
- Stripe: Add more payment gateways for subscriptions

## v1.3.3

Released: 2022-12-20

Web/API:

- Display exact amount when showing the donation goal progress
- Make new server API keys to use the `integration_token` property
- Regulary check for new subscription payments
- Fix 500 error that could happen when creating a membership
- Fix legal page not working on a new instance
- Fix footer and page title not working on first visit of the webpage
- Rework GeoIP
- Update translations

Garry's Mod:

- Fix warning reason not correctly transmitted when using the in-game dashboard
- Fix problems with `ply:SetUserGroup` when no admin addon is used
- Improve some console messages

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

- **Important:** Due to a problem with the latest update, the admin menu in the navigation is visible for all users. To
  fix this, go to the navigation settings, edit the admin menu entry and insert `admin_menu` as required property.
  ***This problem only occurs when the instance has been upgraded from 1.2.x to 1.3.0.***

## v1.3.0

Released: 2022-11-23

Web/API:

- Improve navigation settings by allowing to create sub-menus and by limiting access with requirement sets.
- Make it possible to add navigation links to footer and help-menu
- Fix icon picker

Garry's Mod:

- Add warning/ban dashboard for Garry's Mod (`!dashboard`)
- Make it possible to translate on [translate.matebyte.com](https://translate.matbyte.com/projects/vyhub/vyhub-gmod/).
  More parts will be translatable soon.
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

- If you used PayPal in the past, you need to add the webhook id in the settings. Follow
  the [guide](guide/shop/payment_gateway.md).
- The following game integrations need an update:
    - Garry's Mod

## v0.4.3-beta

Released: 2022-05-04

- Group mappings can no be created without a serverbundle (mapping is then valid for all bundles)
- Fix discord bot creating too much invitations
- Update translations
- Smaller fixes

Update notes:

- The permissions of the Discord bot changed. Either remove and re-add the bot to your server or add the "Manage
  channels" permission to the bot role.

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
