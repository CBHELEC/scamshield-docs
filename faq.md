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

### Can I adjust detection sensitivity?

Yes. The casino detection threshold is configurable in the dashboard (default: 5). Lower values increase sensitivity. Support/Intro/QuickScam engines use fixed thresholds.

## Configuration

### How do I configure the bot?

Use the web dashboard at [https://dashboard.scamshield.lol](https://dashboard.scamshield.lol). Log in with Discord and select your server.

### How do I set up automatic actions?

In the dashboard, use the Casino and Support tabs to configure action chains. Actions execute in order: delete, warn, timeout, kick, ban.

### Can I have different actions for different scam types?

Yes. Casino scams have their own action chain (`actions`), and Support/Intro/QuickScam share a separate action chain (`support_actions`).

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

### The dashboard shows an error

Check that the bot and dashboard are both running and the IPC connection is working. Visit the dashboard's `/debug/ipc-test` endpoint to test connectivity.

## Troubleshooting

### Commands not showing up

Run `/dev sync` to resynchronize global slash commands. This requires developer permissions.

### Bot not responding

Check:

- The bot is online in Discord
- `s.ping` returns a response
- The bot has proper channel permissions

### False positives

If the bot is flagging legitimate messages, you can:

- Increase the casino detection threshold
- Disable specific detection types
- Remove overly broad actions (like ban) from the action chain
- Report the false positive to the development team