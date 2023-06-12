# Properties

The property system is responsible for managing access permissions and more.

Every group has a set of properties that are applied to a user if the user is a member in the group. Some component (like warnings, bans) will also check if the user has the required property in a specific bundle.

> **Example:** A user needs the `ban_show` property to see bans for a bundle. The user can only see the bans of the bundles, where it has the property applied (by a group membership).

For most functions, it is enough to have the required property in only one serverbundle.

## Default Properties

It is possible to assign users with default properties. Users (also non-logged-in) inherit the properties from the serverbundle `default_group`.

> Default properties also apply to non-logged-in users.

**Example**: Every user can display serverbundle specific bans, when the serverbundle's default group has the `ban_show` property.

## Additional infos for developers

> The features below are not yet implemented in the web UI and may be overwritten when editing a group via the web UI.

You can add custom properties via the API if you want.

There is also an advanced feature which allows to add negative (`granted` set to `false`) properties. A negative property from one group overwrites a positive property from another group and results in the user not having the property.

It is also possible to apply a value to a property.
