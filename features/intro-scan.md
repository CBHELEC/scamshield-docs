---
title: "Fake Introduction Detection"
description: "Detects scammers posing as new members who pitch business opportunities."
icon: "user-plus"
---

# Fake Introduction Detection

The IntroScan engine identifies messages that look like innocent introductions but are actually business opportunity pitches designed to move victims to DMs.

## How It Works

Messages are analyzed using the **Fake Introduction / Business Pitch** pattern group from `_scam_patterns.py`. The minimum score threshold is 30.

### Detected Patterns

- Business opportunity, venture, or model pitches seeking partners
- "Looking for reliable/serious/trustworthy" partner language
- "No investment required" or "without any investment" claims
- Side hustle, financial freedom, multiple income source references
- Self-development language combined with business or financial terms
- "Building something meaningful/long-term/big" phrasing
- "Feel free to DM" / "don't be shy" calls to action
- Location-based intros ("I'm from...") combined with networking requests
- Student + side hustler combinations

### Example Detected Messages

Messages that combine a friendly introduction with money-making claims or business pitch language are flagged. The engine specifically targets the pattern of:

1. Establishing social presence ("I'm [name] from [place]")
2. Building rapport ("feel free to say hi")
3. Introducing money/business angle ("started a business", "earning $X")
4. Moving to DMs ("send a request", "message me")

## Configuration

Uses the same configuration as Support scam detection:

- **Actions** — Delete, warn, timeout, kick, ban
- **Alerts** — Toggle alert embeds, set channel, configure ping roles

## Message Triggers

Analyzes text content of messages in server channels (DMs are not analyzed by this engine).
