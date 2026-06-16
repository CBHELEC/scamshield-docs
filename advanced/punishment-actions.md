---
title: "Punishment Actions"
description: "The action chain system and interactive moderation."
icon: "gavel"
---

# Punishment Actions

ScamShield uses a configurable action chain system for handling detected scams, plus an interactive moderation dropdown on every alert embed.

## Action Chains

Each detection type (casino, support/intro/quick) has an independent action chain configured via the web dashboard. Actions execute in order. If an action fails (e.g., missing permissions), the chain continues to the next action.

### Available Actions

| Action | Description | Parameters |
|---|---|---|
| Delete | Removes the flagged message | None |
| Warn | Records a warning in the database | None |
| Timeout | Mutes the user temporarily | Duration in minutes |
| Kick | Removes the user from the server | None |
| Ban | Permanently bans the user | Delete days (message history to remove) |

### Best Practices

- **Delete should be first** — Removes the scam message before other actions execute
- **Warn before kick/ban** — Builds a record of the user's infractions
- **Timeout for first offenses** — Less aggressive than immediate kicks or bans

## Interactive Moderation

Every alert embed includes a **PunishmentView** with a dropdown menu for interactive moderation. Moderators with the `Moderate Members` permission can:

- **Ban** — Permanently ban the user (with configurable delete days)
- **Kick** — Remove the user from the server
- **Timeout** — Mute the user for a duration
- **Unmute** — Remove an active timeout
- **Unban** — Reverse a ban
- **Warn** — Issue a manual warning
- **Unwarn** — Remove a specific warning (opens a sub-menu to select which warning)

### How It Works

1. A detection alert is posted with the punishment dropdown
2. A moderator selects an action from the dropdown
3. A modal appears for any required details (reason, duration)
4. On submission, the action is executed and the result is posted as a reply to the alert
5. The view is disabled after the action to prevent duplicate executions
