# Packets

> A packet needs to be assigned to a category.

| Attribute              | Description                                                                                |
|------------------------|--------------------------------------------------------------------------------------------|
| Title                  | Title of packet                                                                            |
| Subtitle               | Subtitle of packet                                                                         |
| Category               | Category the packet is assigned to                                                         |
| Enable                 | If disabled, packet can not be bought and all bought packets become inactive               |
| Abstract               | Bullet points to describe the packet                                                       |
| Description            | Packet description                                                                         |
| Image Url              | Image shown in the shop                                                                    |
| Active for             | The time the rewards are active for (Recurring payments possible)                          |
| Buyable                | If disabled, packet can not be bought anymore                                              |
| Buyable active state   | If disabled, packet can not be purchased if the user already has this packet active        |
| Buyable inactive state | If disabled, packet can not be purchased if the user already has this packet, but inactive |


## Packet Categories

| Attribute | Description             |
|-----------|-------------------------|
| Name      | Name of category        |
| Image URL | Image shown in the shop |
| Enabled   | Enable the category     |


## Packet Relations

> This setting allows to create relations between packets

**Example:**  

- Packet A is needed to buy Packet B
- Packet A disables Packet B
- Packet A can not be bought when Packet B is active

## Payment

| Attribute                        | Description                                                                                                                                                            |
|----------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Price                            | Price of packet                                                                                                                                                        |
| Currency                         | Your currency                                                                                                                                                          |
| Credits                          | If you want to accept credits (leave empty if not)                                                                                                                     |
| Custom Price / Pay what you want | (Not supported yet) The user can decide how much he is going to pay                                                                                                    |
| Recurring                        | Recurring payments every time the **active for** duration is expired - this limits the choice of payment gateways to these that support it. Currently **Stripe** and **PayPal**. |
