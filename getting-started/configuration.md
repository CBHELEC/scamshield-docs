---
title: "Configuration"
description: "How to configure ScamShield for your server."
icon: "sliders"
---

# Configuration

ScamShield offers per-server configuration through the **web dashboard**. Each detection type has independent settings for actions, alerts, and channels.

## Configuration Methods

### Web Dashboard (Recommended)

The web dashboard provides a full GUI for managing all settings:

1. Visit the dashboard URL ([https://dashboard.scamshield.lol](https://dashboard.scamshield.lol))
2. Log in with your Discord account
3. Select your server
4. Configure each tab

See the [Web Dashboard](/dashboard/index) section for detailed guides on each tab.

### Slash Commands

`/config` — Sends a link to the web dashboard.

## Configuration Overview

Each detection type has three configurable components:

### Action Chain

What happens when a scam is detected. Actions run in order:

| Action | Description |
| --- | --- |
| Delete | Remove the scam message |
| Warn | Record a warning in the database |
| Timeout | Mute the user for a set duration |
| Kick | Remove the user from the server |
| Ban | Permanently ban the user |

Action timing: **Delete should be first** in the chain to remove the message before other actions. Subsequent actions (warn, timeout, kick, ban) execute on the user.

### Alert Settings

- **Toggle** — Enable or disable alert embeds
- **Channel** — Choose which channel receives alerts
- **Ping Roles** — Roles to mention when an alert is sent