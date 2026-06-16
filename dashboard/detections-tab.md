---
title: "Detections Tab"
description: "View and manage detection history."
icon: "list"
---

# Detections Tab

The Detections tab displays a searchable log of all scam detections in your server.

## Detection Log

Each entry shows:

| Column | Description |
|---|---|
| ID | Unique detection identifier |
| User | Username and discriminator of the flagged user |
| Type | Detection type (casino, support, intro, quick_scam) |
| Score | Detection score at time of flagging |
| Confidence | Confidence percentage |
| Action | Action taken (delete, warn, timeout, kick, ban) |
| Time | Timestamp of detection |

### Deleting a Detection

Click the **Delete** button next to any detection entry to remove it from the log. This does not undo any actions taken — it only removes the database record.

The detection log is paginated and sorted newest-first.
