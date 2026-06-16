---
title: "Casino Tab"
description: "Configure casino scam detection settings."
icon: "gamepad-2"
---

# Casino Tab

The Casino tab controls detection settings for celebrity-endorsed casino scams.

## Settings

### Alert Toggle

Enable or disable alert embeds for casino scam detections. When disabled, the bot still executes configured actions but doesn't post an alert.

### Alert Channel

Select the channel where detection alerts are posted. If not set, alerts go to the system message channel.

### Ping Roles

Select roles that are mentioned when an alert is posted. Useful for notifying moderators.

### Detection Threshold

Set the score threshold (1–20). Default is 5. Lower values increase sensitivity. The threshold affects whether a message is flagged as a casino scam.

### Action Chain

Configure what happens when a casino scam is detected. Actions run in order:

1. **Delete** — Removes the scam message
2. **Warn** — Records a warning in the database
3. **Timeout** — Mutes the user (set duration in minutes)
4. **Kick** — Removes the user from the server
5. **Ban** — Permanently bans the user

You can add, remove, and reorder actions. Each action type has its own configuration parameters (like timeout duration in minutes).
