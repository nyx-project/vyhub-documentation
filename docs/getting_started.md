# Getting Started

This is the quickstart guide. For additional information read our further guides.

## Get your VyHub Instance

Using VyHub for your gaming community is as easy as a few clicks are.  
Create your account on [VyHub.net](https://vyhub.net) and choose one of our packets.  
Your VyHub instance is usually created within a few minutes.

## Open your VyHub Instance

Congratulations you can now connect and login to your VyHub instance under the domain you have chosen in the installation process.  
All further steps are accomplished within the settings panel of your VyHub instance  
**(your-domain.com/settings)**

## Connect your Gameserver

One of the first things to do is to connect your gameserver with VyHub.

> Each gameserver is organised in a [serverbundle](/guide/server.md "Server").  
> All server within a serverbundle are from the same type (e.g. GMOD, Teamspeak, Discord) 

1.  Navigate to the **server** settings and create your serverbundle.  
    We are going to choose the default group for new users in this bundle later.
2.  Now it's time to connect your server, which is done in the same settings menu.  
    Follow the displayed instructions.


[*Additional Information*](/guide/server.md)

## Groups

After you have created your first serverbundle you need to create your first group.  

> A [group](/guide/group.md "Group") has [properties](/guide/properties.md "Properties") to control the user right management and access control.

1. Navigate to the **group** settings and create your group.  
   - The permission level is used to decide which users can be targeted by a member of the group  
     - e.g. A user with permission level 42 can't target another user with the level of 99.  
   - The admin flag sets **all** rights.
2. Now edit the created group, switch to the **properties** tab and choose all needed properties.  
   A list of all properties and it's functions can be found [here](/guide/properties.md "Properties").
3. Go back to the server tab, edit your serverbundle and choose your created group as default group.


[*Additional Information*](/guide/group.md)

## Shop

### Reward

> A reward may execute a server-command, run a script or add credits to a user account.   
> Rewards are applied after a packet containing this reward is purchased.

Create a reward in the **reward** settings.

### Packet

> Your created [packets](/guide/packets.md "Packets") are available for purchase by your users.

Packets are ordered within categories. Categories are created in the **category** settings.  
A price is set in the **payment** tab.

- Do not forget to select the **rewards** the user can buy with the packet.

[*Additional Information*](/guide/packets.md "Packets")

### Payments and Tax

#### Payment Gateway / Payment Methods

Payment methods (e.g. Paypal, Stripe) available for your customers can be added in the **payment gateway** settings.  
> You need to provide the VyHub instance with the payment providers **secrets**.

These secrets can be obtained directly from the payment provider after creating an account with them.

#### Tax

> For correct taxation of your sales, tax rules for your country have to be created.

To provide the correct tax information go to the **tax** settings.

## Customize your Community

Congratulations you are all set up!

VyHub is customizable for your needs.  
Try changing the theme in the **theme** settings or start creating your own pages in the **navigation** settings. 
