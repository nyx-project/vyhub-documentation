# Groups

Groups are used to organize users and assign permissions to them. The use of this feature is optional and depends on
your use case.

## Attributes

| Attribute           | Description                                                         |
|---------------------|---------------------------------------------------------------------|
| Permission Level    | Used to determine the ability to target other users                 |
| Max Ban Length      | [Optional] Max length of bans the user can create                   |
| Is Team             | Whether the group will be shown on the team overview page           |
| Properties          | Permission management and access control for functionalities        |
| Negative Properties | [Advanced] Negative properties (e.g. ban players from your website) |
| Mappings            | Mappings from VyHub groups to server/in-game ranks/groups/roles     |

## Assigning Groups

Groups can be assigned to users in the `User Dashboard` in the group section.
Furthermore, groups can be used as a reward in the shop can be assigned automatically through the
`VyHub Group` [shop reward](../shop/reward.md).

## Properties

Properties are used to control the user right management and access control. They can be used to restrict access to
certain pages, features, or actions. For example, only user groups with the `ban_create` property can create bans
through the website.

Learn more about properties in the [properties](./property.md) guide.

## Group Mappings

Group mappings are essential for the synchronization of groups on your servers when using the `VyHub Group Sync` and not
using simple commands. Learn more about the `VyHub Group Sync` in the [group sync](./group_sync.md) guide.

Without a Group Mapping, it is not clear which VyHub group belongs to which server group(s). Therefore, the Sync cannot
work.

A group mapping consists of two parts:

1. Serverbundle: The group mapping is scoped for this serverbundle. Leave empty to make the mapping valid for all
   bundles.
2. Name of group/rank/role: The name of the group/rank/role on your server.

### Example

Imagine that there are two serverbundles: One for Garry's Mod and one for Discord.

- We want that users that have the `Admin` VyHub group in the GMOD serverbundle should receive the `superadmin` in-game.
- Additionally, users that have the `Admin` VyHub group in the Discord serverbundle should receive the `Owner` role on
  the Discord server.

We go to the `Mappings` section of the `Admin` VyHub group and create two mappings:

- One for the GMOD serverbundle with `superadmin` as group name.
- One for the Discord serverbundle with `Owner` as group name.
