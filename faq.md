---
title: "FAQ"
description: "Frequently asked questions about ScamShield."
icon: "question-circle"
---

# Frequently Asked Questions

## General

### What scams does ScamShield detect?

ScamShield detects five categories: celebrity casino scams, support/masked URL scams, fake introduction/business pitch scams, get-rich-quick scams, and you can manually check any message with `/check`.

### Does the bot read all my messages?

Yes, the bot reads message content in channels it has access to. It only processes messages for scam detection and does not store or share message content outside of detection logs.

### Can I use both slash commands and prefix commands?

Yes. Slash commands (`/help`, `/ping`, etc.) and prefix commands (`s.help`, `s.ping`) are both available.

## Detection

### What triggers each detection engine?

Each engine has different triggers:

- **Casino** — Messages with image attachments containing casino promo visuals \+ text
- **Support** — Any message with masked/obfuscated URLs
- **IntroScan** — Text messages matching fake introduction patterns
- **QuickScam** — Text messages matching get-rich-quick patterns
- **ScamScan** — Manual invocation via `/check`

### Why was a message flagged?

Review the alert embed for details on which signals were detected, including specific pattern names and scores.

### Why wasn't a scam detected?

ScamShield uses pattern-based detection. If a scam uses novel phrasing or techniques not covered by existing patterns, it may not be detected. You can use `/check` to test messages. Report missed detections to the development team.

## Configuration

### How do I configure the bot?

Use the web dashboard at [https://dashboard.scamshield.lol](https://dashboard.scamshield.lol). Log in with Discord and select your server.

### How do I set up automatic actions?

In the dashboard, use the Casino and Support tabs to configure action chains. Actions execute in order: delete, warn, timeout, kick, ban.

## Permissions

### What permissions does the bot need?

The bot needs: Read Messages, Send Messages, Manage Messages, Moderate Members, Read Message History, Attach Files, Embed Links, and Use External Emoji.

### Why isn't the bot taking action?

Check that:

1. The bot has the required permissions in the channel and server
2. Actions are configured in the dashboard
3. The bot is not rate-limited by Discord

## Dashboard

### I can't see my server in the dashboard

Ensure you have **Administrator** permission in the server and the bot is a member.

## Troubleshooting

### Bot not responding

Check:

- The bot is online in Discord
- `s.ping` returns a response
- The bot has proper channel permissions

### False positives

If the bot is flagging legitimate messages, you can:

- Use the button on the alert to report it to the development team