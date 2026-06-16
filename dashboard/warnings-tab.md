---
title: "Warnings Tab"
description: "View and manage user warnings."
icon: "alert-triangle"
---

# Warnings Tab

The Warnings tab displays all warnings issued by ScamShield in your server.

## Warning Log

Each entry shows:

| Column | Description |
|---|---|
| ID | Unique warning identifier |
| User | Username and discriminator of the warned user |
| Moderator | Who issued the warning (usually the bot) |
| Reason | Why the warning was issued |
| Time | Timestamp of warning |

### Deleting a Warning

Click the **Delete** button next to any warning entry to remove it from the log. This does not undo any actions taken — it only removes the database record.

### Clearing Warnings

To clear all warnings for a specific user:

1. Enter the user's Discord ID in the **Clear Warnings** form
2. Click **Clear**
3. All warnings for that user are removed

This is useful for resetting a user's warning history after they've been dealt with manually.
