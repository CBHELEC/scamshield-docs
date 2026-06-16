---
title: "Moderation"
description: "View warning and detection history for server members."
icon: "scale"
---

# Moderation

ScamShield tracks every detection and warning in a searchable database. Use the `/warns` and `/history` commands to review user records.

## Commands

### /warns

Shows all warnings issued to a specific user.

```
/warns user: @username
```

Displays:
- Total warning count
- Up to 10 most recent warnings with timestamps
- Reason for each warning
- Moderator who issued the warning

### /history

Shows all scam detections recorded for a specific user.

```
/history user: @username
```

Displays:
- Total detection count
- Up to 10 most recent detections with timestamps
- Detection type (casino, support, intro, quick_scam) with emoji
- Score and confidence percentage
- Action taken (delete, warn, timeout, kick, ban)

## Permissions

Both commands are available to **all server members**. They return ephemeral responses (only the command user sees the result).

## Warning Sources

Warnings are issued automatically when the action chain for a detection includes the "warn" action. They can also be issued manually via the punishment dropdown on alert embeds.
