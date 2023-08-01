# Groups

## Attributes

| Attribute           | Description                                                     |
|---------------------|-----------------------------------------------------------------|
| Name                | Name of group                                                   |
| Permission Level    | Used to determine the ability to target other users             |
| Max Ban Length      | [Optional] Max length of bans the user can create               |
| Color               | Display color of group on VyHub and gameservers                 |
| Is Team             | Whether the group will be shown on the team overview page       |
| Properties          | Permission management and access control for functionalities    |
| Negative Properties | [Advanced] Negative properties to ban palyers from your website |
| Mappings            | Mappings from VyHub groups to server/in-game ranks/groups/roles |


## Group Mappings
Group mappings are essential for the synchronization of groups on your servers. With them, you can specify which VyHub group belongs to which server group(s).

A group mapping consists of two parts:

1. Serverbundle: The group mapping is scoped for this serverbundle. Leave empty to make the mapping valid for all bundles.
2. Name of group/rank/role: The name of the group/rank/role on your server.

### Example
Imagine that there are two serverbundles: One for Garry's Mod and one for Discord.

- We want that users that have the `Admin` VyHub group in the GMOD serverbundle should receive the `superadmin` in-game.
- Additionally, users that have the `Admin` VyHub group in the Discord serverbundle should receive the `Owner` role on the Discord server.

We go to the `Mappings` section of the `Admin` VyHub group and create two mappings:

- One for the GMOD serverbundle with `superadmin` as group name.
- One for the Discord serverbundle with `Owner` as group name.


## Membership
With memberships, users can be assigned to a group in a serverbundle for a specified amount of time.

### Attributes

| Attribute    | Description                              |
|--------------|------------------------------------------|
| Begin        | Begin of membership                      |
| End          | End of membership (empty if unlimited)   |
| Serverbundle | Serverbundle of membership               |
| Group        | Group on which the membership is applied |


### Add

Memberships can be added by clicking on the `Add` button on the `User Dashboard` in the group section.

### Edit

Memberships can be edited by clicking on the `Edit` button on the `User Dashboard` in the group section.  
All memberships belonging to a group can also be found in the `Group` settings panel.

