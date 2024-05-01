# Rewards

Rewards can be used to execute custom functionality when a user purchases a packet.

> A reward needs to be assigned to a packet to be able to be sold.

| Attribute                                 | Description                                                                           |
|-------------------------------------------|---------------------------------------------------------------------------------------|
| Name                                      | Name of reward                                                                        |
| Serverbundle                              | Serverbundle which the reward is assigned to (reward is executed on all servers in this bundle by  default)                                          |                          |
| Only execute once                         | Reward is only executed once per server (including newly added servers)                                          |
| Only execute on one Server                | Reward is only executed on one server in the serverbundle (must be paired with the previous option)                            |
| Execute again if packet has been extended | Execute this reward again if the packet got extended (e.g. by a subscription payment) |
| Type                                      | Reward Type           
| Event                                     | Event on which the reward functionality is executed  
| Limit to servers                          | Limit the reward to specific servers in the serverbundle (select the bundle first)    |


## In-Game Rewards
Some reward types are executed on the connected servers.
The serverbundle setting defines on which servers the reward is executed.

Usual in-game reward types are `COMMAND` and `SCRIPT`.
For these types, string replacements can be used to insert player-specific data into the command or script.
The game-specific replacements are available in the docs of the integrations.

## Manual Rewards
Rewards can be added manually to users by applying them to an applied packet.

### Packets
Packets can be applied to a user from within the `Add applied packet` dialog. This dialog can be found in the `Shop Administration` -> `Applied Packets` -> `Add applied packet`

### Credits
Credits can be manually added or removed from within the `User Dashboard` -> `Purchases` -> `Credits`.

> It is possible to remove credits by entering a negative number of credits (e.g. -100 credits).

## HTTP Rewards

HTTP rewards can be used to send a HTTP request to a custom URL when a user purchases a packet.
They can be used to integrate with custom systems.

## Variable Replacements

For HTTP rewards and RCON server rewards, the following variable replacements can be used to insert user-specific data into the URL or command.
For all other supported games, the replacements are documented in the respective game documentation.

> **Important:** If you want to make sure that the replacements contain the data of
 a specific user type (e.g. STEAM), select a serverbundle for the reward that belongs to the user type. Due to the architecture of VyHub, a user can have different accounts connected. If no serverbundle is selected for the reward, the user type is not guaranteed as the purchasing user account is used for replacements then.

The following variables within the URL are replaced:

- `%user_id%`: The VyHub user id
- `%user_type%`: The type of the VyHub user (e.g. STEAM, DISCORD, MINECRAFT, ...)
- `%user_identifier%`: The users identifier (e.g. steamid, discord id, minecraft uuid, ...)
- `%username%`: The users nickname
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
- `%currency_code%`: The currencies code
- `%currency_symbol%`: The currencies symbol




