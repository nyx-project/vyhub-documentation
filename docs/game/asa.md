# Ark Survival Ascended
Download Link:
[https://github.com/matbyte-com/vyhub-ark-sa/releases](https://github.com/matbyte-com/vyhub-ark-sa/releases)

## Features

- Shop / Donation Store
- Collect Playtime of your players

> The ASA plugin only supports the listed features. Other features are not (yet) implemented. Feel free to open pull requests and contribute to the plugin.

## Installation

1. In VyHub open the `Add Server` dialog in the `Server` settings and create the server.
2. Click on the `Setup` button of the server and follow the instructions.
3. Optionally, adjust the config files to your needs.

### Libcrypto and Libssl

`Libcrypto.dll` and `Libssl.dll` have to be present on your system. When they are not, the plugin will not load. Place them in the same folder as `AsaApiLoader.exe`.

## Rewards
For Ark Survival Ascended, the following types of rewards are supported:

- `COMMAND`: Executes a console command on the server

### Available replacements
The following string replacements are available for rewards:

- `%user_id%`: The VyHub user id
- `%nick%`: The players in-game nickname
- `%player_id%`: The players minecraft UUID
- `%player_ip_address%`: The players IP address
- `%applied_packet_id%`: The id of the applied packet
- `%packet_title%`: The title of the packet
- `%purchase_amount%`: Total amount with currency of the purchase. For example `30 EUR`.

## Commands

- `/vylogin <token>`: Login to the VyHub website with a given token
- `/vh_setup <api-key> <api_url> <server_id> <serverbundle_id>` Setup command (only functional in server-console)
