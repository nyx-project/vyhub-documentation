# User Dashboard

The user dashboard shows important information about the selected user.

## URLs

The dashboard is available under the following URLs:

- `https://<frontend-url>/dashboard`: The dashboard of the currently logged-in user.
- `https://<frontend-url>/user/<user-id>`: The dashboard of the VyHub user with ID `<user-id>`.
- `https://<frontend-url>/profile/<provider>/<id>`: The dashboard of the `<provider>` user with ID `<id>`. 

    For example: `https://<frontend-url>/profile/steam/76561197960287930`

## Tabs
The user dashboard consists of multiple tabs:

### General

- **Packets:** List of the users applied packets.
- **Statistics:** Graph that shows the history of user attributes with `type=ACCUMULATED` and `unspecific=True`.
- **Avatar:** Avatar of the user and all linked users. Also indicated if the user is an instance admin.
- **Groups:** List of all active groups per serverbundle. Also shows active properties and group memberships.
- **Linked users:** Information about all linked user accounts, including user attributes with `unspecific=True`.
- **Bans and Warnings:** Number of bans and warnings.
- **User Log:** User related logs.

### Purchases

- A list of all purchases of the user with the ability to download invoices
- **Credits:** History of credit payments and option to add credits

### "Serverbundle"

A tab for each serverbundle that shows serverbundle specific information.

- **Statistics:** Graph that shows the serverbundle specific history of user attributes with `type=ACCUMULATED`.
- **Linked users:** Information about relevant linked user accounts, including user attributes for the serverbundle.
- **Bans and Warnings:** Number of bans and warnings in the selected serverbundle.