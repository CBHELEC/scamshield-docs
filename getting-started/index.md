---
title: "Getting Started"
description: "Overview of setting up ScamShield for your Discord server."
icon: "rocket"
---

# Getting Started

ScamShield is designed to work out of the box with minimal setup. Once the bot is in your server, it immediately starts monitoring messages for scam content.

## What You'll Need

- A Discord server where you have **Manage Server** permissions
- The bot invite link from the [ScamShield website](https://scamshield.lol)

## Setup Process

1. **Invite the bot** — Use the invite link and authorize it for your server
2. **Configure actions** — Visit the web dashboard to set up what happens when scams are detected
3. **Set an alert channel** — Choose where detection alerts are posted
4. **Done** — The bot works silently in the background

## Detection Coverage

By default, all detection engines are active:

| Engine | What It Detects | Message Trigger |
|---|---|---|
| Casino | Celebrity-endorsed casino promos | Images with text |
| Support | Obfuscated/masked Discord support URLs | Text with hidden URLs |
| IntroScan | Fake introduction posts pitching business opportunities | Text |
| QuickScam | Get-rich-quick investment promises | Text |
| ScamScan | Manual `/check` command analysis | Text or images |

## Next Steps

- [Installation guide](/getting-started/installation) — Detailed invite and setup instructions
- [Configuration](/getting-started/configuration) — Customize detection per your server
- [Web Dashboard](/dashboard/index) — Full configuration via the dashboard
