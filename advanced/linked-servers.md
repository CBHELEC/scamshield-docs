---
title: "Linked Servers"
description: "Cross-server propagation of scam detection actions."
icon: "link"
---

# Linked Servers

The linked server system allows ScamShield to propagate scam detection actions across multiple servers, automatically taking action on known scammers wherever they appear.

## How It Works

When a scam is detected in any server:

1. ScamShield identifies all other servers where both the bot and the flagged user are present
2. For each server with **linked accept enabled**, the bot reads that server's configured **linked actions**
3. The configured actions (warn, timeout, kick, ban) are executed in the linked server
4. An alert is sent to the linked server's configured alert channel
5. The results are shown in the **original server's** alert embed

## Configuration

Linked server settings are configured per-server via the **General** tab in the web dashboard.

| Setting | Description |
|---|---|
| Accept Linked Detections | Enable to accept and act on detections from other servers |
| Linked Actions | Actions to take on the user (warn, timeout, kick, ban) |

Linked actions cannot include "delete" since the original message is in a different server.

## Use Cases

- **Multi-server moderation** — Keep serial scammers out of all your communities
- **Early warning network** — If a scammer is caught in one server, other servers in your network are automatically protected
- **Shared ban lists** — Effectively create a shared ban list across servers

## Detection Types

Linked propagation preserves the detection type (`casino`, `support`, `intro`, `quick_scam`), so the linked server's alert embed accurately reflects what type of scam was detected.
