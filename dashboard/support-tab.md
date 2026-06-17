---
title: "Support Tab"
description: "Configure support scam, intro scan, and quick scam detection settings."
icon: "messages-question"
---

# Support Tab

The Support tab controls detection settings for three engines:

- **Support / Masked URL Scams**
- **Fake Introduction / Business Pitch Scams**
- **Get-Rich-Quick Scams**

These three detection types share the same configuration because they all handle text-based scam detection. Each has separate logging in the database with distinct `detection_type` values (`support`, `intro`, `quick_scam`).

## Settings

### Alert Toggle

Enable or disable alert embeds for these detection types.

### Alert Channel

Select the channel where detection alerts are posted. If not set, alerts go to the system message channel.

### Ping Roles

Select roles that are mentioned when an alert is posted.

### Action Chain

Configure what happens when one of these scams is detected. Actions run in order:

1. **Delete** — Removes the scam message
2. **Warn** — Records a warning in the database
3. **Timeout** — Mutes the user (set duration in minutes)
4. **Kick** — Removes the user from the server
5. **Ban** — Permanently bans the user