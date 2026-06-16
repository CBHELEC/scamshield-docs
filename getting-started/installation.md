---
title: "Installation"
description: "How to invite ScamShield to your Discord server and verify it's running."
icon: "download"
---

# Installation

## Inviting the Bot

1. Visit [https://scamshield.lol](https://scamshield.lol) and click the **Invite** button
2. Select your Discord server from the dropdown
3. Review the requested permissions
4. Click **Authorize**

## Required Permissions

The bot needs the following permissions to function:

| Permission | Purpose |
|---|---|
| Read Messages / View Channels | Read message content in monitored channels |
| Send Messages | Send alert embeds and notifications |
| Manage Messages | Delete flagged scam messages |
| Moderate Members | Timeout, kick, or ban scammers |
| Read Message History | Check edited messages for scam content |
| Attach Files | Include evidence in alert embeds |
| Embed Links | Send rich embed alerts |
| Use External Emoji | Display detection emoji indicators |

## Verifying the Bot Is Online

Once invited, check that the bot is working:

1. The bot should appear as online in your member list
2. Type `s.ping` in any channel — the bot should reply with `Pong!` and its latency
3. If using slash commands, try `/ping`

## Permissions Issues

If the bot doesn't respond, check:

- The bot has **Read Messages** permission in the channel
- The bot has **Send Messages** permission
- Your server has enabled **Use Slash Commands** permission for members

## Prefix Commands

The bot's prefix is `s.`. For example:

- `s.help` — Show command list
- `s.ping` — Check bot latency

Slash commands (like `/help`, `/warns`, `/check`) are also available.
