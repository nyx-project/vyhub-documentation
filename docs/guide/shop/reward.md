# Rewards

Rewards are executed when a user purchases a packet. They can be used to give users in-game items, ranks, or execute
HTTP requests.

> A reward needs to be assigned to a packet to be able to be bought by your players / your customers.

| Attribute                                 | Description                                                                                                |
|-------------------------------------------|------------------------------------------------------------------------------------------------------------|
| Serverbundle                              | Serverbundle which the reward is assigned to (reward is executed on all servers in this bundle by default) |                          |
| Only execute once                         | Reward is only executed once per server (including newly added servers)                                    |
| Only execute on one Server                | Reward is only executed on one server in the serverbundle (must be paired with the previous option)        |
| Execute again if packet has been extended | Execute this reward again if the packet got extended (e.g. by a subscription payment)                      |
| Event                                     | Event on which the reward functionality is executed                                                        |
| Limit to servers                          | Limit the reward to specific servers in the serverbundle (select the bundle first)                         |

## Testing your Rewards

To test your rewards, assign them to a packet.

After that, you have two options to test the rewards:

**Option 1**

Buy the packet in the shop. For example, use a 100% discount, or use a credit gateway.

**Option 2**

You can also manually apply the packet to the user.

Go to the  `Add applied packet` dialog. This dialog can be found in the
`Shop Administration` -> `Applied Packets` -> `Add applied packet`

## In-Game Rewards

VyHub works by executing commands on your server when a user buys a [packet](./packet.md).

Usual in-game reward types are `COMMAND` and `SCRIPT`.

For these types, string replacements can be used to insert player-specific data into the command or script; furthermore,
the User needs to be connected to the server.

The game-specific replacements are available in the docs of the game [integrations](../../game/integrations.md).

## Group Membership Rewards

Group membership rewards can be used to assign a user to a group on your server when they purchase a packet.

The use of the membership rewards is optional, you can also use the simple `COMMAND` reward type to assign groups.

Read more about the differences between the user sync and the commands in the [group](../group/group_sync.md)
documentation.

## HTTP Rewards

HTTP rewards can be used to send an HTTP request to a custom URL when a user purchases a packet.
They can be used to integrate with custom systems.

## Variable Replacements

For HTTP rewards and RCON server rewards, the following variable replacements can be used to insert user-specific data
into the URL or command.
For all other supported games, the replacements are documented in the respective game documentation.

> **Important:** If you want to make sure that the replacements contain the data of
> a specific user type (e.g., STEAM), select a serverbundle for the reward that belongs to the user type. Due to the
> architecture of VyHub, a user can have different accounts connected. If no serverbundle is selected for the reward,
> the
> user type is not guaranteed as the purchasing user account is used for replacements then.

The following variables within the URL are replaced:

- `%user_id%`: The VyHub user id
- `%user_type%`: The type of the VyHub user (e.g., STEAM, DISCORD, MINECRAFT, ...)
- `%user_identifier%`: The users identifier (e.g., steamid, discord id, minecraft uuid, ...)
- `%username%`: The user's nickname
- `%serverbundle_name%`: The serverbundle name
- `%serverbundle_id%`: The serverbundle id
- `%packet_name%`: The packet name
- `%packet_id%`: The packet id
- `%applied_packet_id%`: The applied packet id
- `%purchase_id%`: The purchase id
- `%purchase_amount%`: The purchase amount with currency
- `%purchase_amount_total%`: The purchase total amount
- `%purchase_amount_net%`: The purchase net amount
- `%purchase_amount_tax%`: The purchase tax amount
- `%purchase_amount_credits%`: The purchase credits
- `%currency_code%`: The currency code
- `%currency_symbol%`: The currency symbol




