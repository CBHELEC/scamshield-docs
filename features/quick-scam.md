---
title: "Get-Rich-Quick Detection"
description: "Detects fake investment and money-making promise scams."
icon: "zap"
---

# Get-Rich-Quick Detection

The QuickScam engine identifies messages promising easy money through fake investments, trading schemes, or business opportunities.

## How It Works

Messages are scanned against 13 regex patterns. At least 2 patterns must match to trigger detection.

### Detected Patterns

- **High earnings in short time** — "$Xk within Y hours" structures
- **Limited spots** — "First X people to earn" urgency tactics
- **Reimbursement guarantees** — "Reimburse X% profit"
- **Commission structures** — "X% of your profit/earning/commission"
- **DM requests** — "Send friend request if interested to earn money"
- **Telegram references** — Telegram handle solicitations
- **Learn-how prompts** — "Ask me how", "Want to learn how"
- **Help offers** — "I'll help you earn money"
- **Money + time frequency** — "Earn $XXXX daily/weekly/monthly"
- **Dollar amounts + requests** — "$X ... request/message me"
- **Learn-how + DM combos** — "Want to learn how? Send a request"

### DM Detection

If a scam message is sent via **direct message** (not in a server), QuickScam logs the detection across all guilds in the database. The user is notified their message was flagged.

## Configuration

Uses the same configuration as Support scam detection:

- **Actions** — Delete, warn, timeout, kick, ban
- **Alerts** — Toggle alert embeds, set channel, configure ping roles

## Message Triggers

Analyzes text content of every message, including DMs.
