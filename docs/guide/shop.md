# Shop

## General Settings

| Attribute | Description |
| --- | --- |
| Enable Donation Goal | Display donation goal (displayed on startpage - "News") |
| Donation Goal | Actual value for the donation goal |
| Checkout Checkboxes | Checkboxes which have to be agreed to during checkout |
| Business Address | Address of server owner / business (is displayed on invoice) |

## Tax

> Tax Rules need to be set to be able to sell goods

You can set **tax rules** for each country or for all of them at once.

## Payment Gateway

> You need to create a payment gateway to accept payments.

| Attribute | Description |
| --- | --- |
| Name | Name of gateway |
| Subtitle | Subtitle shown during checkout |
| Enabled | Enable the payment gateway |
| Environment | Environment of gateway (Sandbox / Production) |
| Secrets | Secrets provided by payment providers |

### Types

| Gateway | Information |
| --- | --- |
| Paypal | [Paypal Business](https://www.paypal.com/us/business) |
| Stripe | [Create Stripe Account](https://dashboard.stripe.com/register) |
| Credits | VyHub internal payment method - create packets for players to buy credits |
| Paysafecard | [Become a partner](https://www.paysafecard.com/de/become-a-partner/) |

## Categories

| Attribute | Description |
| --- | --- |
| Name | Name of category |
| Image URL | Image shown in the shop |
| Enabled | Enable the category |

## Packets

> A packet needs to be assigned to a category.

| Attribute | Description |
| --- | --- |
| Title | Title of packet |
| Subtitle | Subtitle of packet |
| Category | Category the packet is assigned to  |
| Enable | If disabled, packet can not be bought and all bought packets become inactive |
| Abstract | Bullet points to describe the packet |
| Description | Packet description |
| Image Url | Image shown in the shop |
| Active for | The time the rewards are active for (Recurring payments possible) |
| Buyable | If disabled, packet can not be bought anymore |
| Buyable active state | |
| Buyable inactive state | |

[//]: # (TODO Explain active and inactive state)

### Payment

| Attribute | Description |
| --- | --- |
| Price | Price of packet |
| Currency | Your currency |
| Credits | If you want to accept credits (leave empty if not) |
| Custom Price / Pay what you want | The user can decide how much he is going to pay |
| Recurring | Recurring payments every time the **active for** duration is expired - this limits the choice of payment gateways to **Stripe**

### Packet Relations

> This setting allows to create relations between packets

**Example:**  
- Packet A is needed to buy Packet B
- Packet A disables Packet B
- Packet A can not be bought when Packet B is active


## Rewards

> A reward needs to be assigned to a packet to be able to be sold.

| Attribute | Description |
| --- | --- |
| Name | Name of reward |
| Serverbundle | Serverbundle which the reward is assigned to |
| Event | Event on which the reward functionality is executed |
| Once / One Server | |
| Type | Reward Type |

