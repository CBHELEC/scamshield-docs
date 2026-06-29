---
title: "Introduction"
description: "ScamShield is a fully automated Discord anti-scam bot that protects your community from 5 major categories of scams in real time."
icon: "shield"
---

# Welcome to ScamShield

ScamShield (UniversalAntiScam) is a Discord bot that automatically detects and acts on scam messages across five detection engines:

- **Celebrity Casino Scams** — Fake casino promos using celebrity endorsements
- **Support / Masked URL Scams** — Obfuscated links impersonating Discord support
- **Fake Introduction / Business Pitches** — Scammers posing as new members
- **Get-Rich-Quick Scams** — Fake investment and money-making promises
- **Manual Scan** — On-demand text and image analysis via `/check`

Each detection engine runs in real-time on every message, with configurable actions (delete, warn, timeout, kick, ban), role-based alerts, and cross-server propagation.

## Key Features

- **5 automated detection engines** covering the most common Discord scam types
- **Image analysis** using pixel-level feature detection and reference comparison
- **Configurable action chains** per detection type per server
- **Interactive moderation** via punishment dropdowns on alert embeds
- **Web dashboard** for full server configuration without touching commands
- **Cross-server propagation** to act on shared scammers across linked servers
- **Detection history and warnings** tracked in a searchable database
- **Slash commands and prefix commands** for easy management

## Quick Start

1. [Invite the bot](/getting-started/installation) to your server
2. [Configure detection settings](/getting-started/configuration) via the dashboard
3. Detection runs automatically — review alerts in your configured channel