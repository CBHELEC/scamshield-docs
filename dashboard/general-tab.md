---
title: "General Tab"
description: "Configure linked server propagation settings."
icon: "link"
---

# General Tab

The General tab controls cross-server propagation settings, which allow scam detection actions to propagate across multiple servers.

## Linked Server Propagation

When a scam is detected in one server, ScamShield can automatically take action in **other servers** where the scammer is also a member.

### How It Works

1. A scam is detected in Server A
2. ScamShield checks all other servers it shares with the scammer
3. For servers with **Linked Accept** enabled, it executes their configured **Linked Actions**
4. Results are shown in the original alert embed

### Settings

| Setting | Description |
|---|---|
| Accept Linked Detections | Toggle whether this server accepts actions from other servers' detections |
| Linked Actions | Actions to take on the user in this server when a linked detection occurs |

### Linked Actions

Unlike Casino and Support action chains, linked actions do **not** include the "delete" option (since the original message is in a different server). Available actions:

- Warn
- Timeout
- Kick
- Ban

### Use Cases

- **Multi-server communities** — If a scammer is banned from one server, automatically ban them from all linked servers
- **Shared moderation** — Detect and act on serial scammers across your server network
- **Early warning** — If a scammer joins one of your servers after being flagged elsewhere, past actions propagate
