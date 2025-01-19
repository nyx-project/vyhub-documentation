# Source (RCON)

This integration can be used with Source servers that support
the [Source RCON Protocol](https://developer.valvesoftware.com/wiki/Source_RCON_Protocol).

## Supported Games / Servers

All games that implement the [Source RCON Protocol](https://developer.valvesoftware.com/wiki/Source_RCON_Protocol) are
supported.

- Counter Strike: Source
- Counter Strike: 2
- Team Fortress 2
- Half-Life 2
- Many more...

## Features

- Shop / Donation Store
- Server Dashboard
- Server Status

## Installation

1. Create a serverbundle for the server type `SOURCE` in the settings
2. In the `Add Server` dialog in the `Server` settings, supply the RCON password and create the server

## Group Sync

> Only direct commands are supported. The plugin does not support `VyHub Group Sync`.

You can sell groups and VIP-ranks through VyHub for your gameserver. Syncing the user groups can be either done through
a command or by using the VyHub Group-Sync feature. Read more about syncing groups in
the [group](../guide/group/group_sync.md) guide.

## Rewards

For Source (RCON), only these rewards are supported:

- `COMMAND`: Executes a console command on the server

### Available replacements

You can find the available replacements [here](../guide/shop/reward.md#variable-replacements).

## Troubleshooting

If something does not work as expected, check the VyHub log.
