---
title: "Detection Features"
description: "Overview of all scam detection engines in ScamShield."
icon: "search"
---

# Detection Features

ScamShield uses five independent detection engines. Each runs on every message and can trigger its own set of actions and alerts.

## Detection Engines

| Engine | File | Detects | Method |
|---|---|---|---|
| Casino | `Casino.py` | Celebrity casino promos | Text + Image analysis |
| Support | `Support.py` | Masked/hidden URLs | Unicode normalization |
| IntroScan | `IntroScan.py` | Fake business pitch intros | Regex pattern matching |
| QuickScam | `QuickScam.py` | Get-rich-quick schemes | Regex pattern matching |
| ScamScan | `ScamScan.py` | Manual `/check` scans | Pattern matching + OCR |

## How Detection Works

1. **Listener** — `on_message` and `on_message_edit` events capture every message
2. **Filter** — Skips bot's own messages, DMs (for some engines), and alert embeds
3. **Analyze** — Runs text and/or images through pattern-matching logic
4. **Threshold** — If the score exceeds the threshold, detection triggers
5. **Actions** — Executes the configured action chain (delete, warn, timeout, kick, ban)
6. **Alert** — Sends a rich embed to the configured alert channel with moderation controls
7. **Log** — Records the detection to the database
8. **Propagate** — Optionally shares detection to linked servers

## Common Patterns

ScamShield's `_scam_patterns.py` contains 15+ pattern groups covering:

- Unsolicited DM Greetings
- Money Deposit / CashApp Scams
- False Report Scams
- Nitro Giveaway Scams
- Giveaway Scams
- Cryptocurrency Scams
- Fake Community Interest
- Support Impersonation
- Suspicious Links
- Urgency Pressure
- Payment / Account Requests
- Art Commission Scams
- Try My Game Scams
- Fake Introduction / Business Pitches
- Suspicious Keywords
