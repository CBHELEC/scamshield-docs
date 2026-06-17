---
title: "Casino Scam Detection"
description: "Detects celebrity-endorsed casino scams using text and image analysis."
icon: "money-bill-1-wave"
---

# Casino Scam Detection

The Casino detection engine identifies fake casino promotions that use celebrity names (MrBeast, Elon Musk, Ronaldo, Taylor Swift, etc.) to lure victims.

## How It Works

The engine uses a two-stage analysis pipeline:

### 1. Text Analysis

Extracts text from the message content, attachment filenames, and embed metadata. It checks for four categories of terms:

| Category | Examples | Score Contribution |
| --- | --- | --- |
| Celebrity | mrbeast, elon, ronaldo, taylor swift, drake, ksi, trump | \+1–3 per term |
| Casino | casino, slots, bonus, promo, wager, rakeback | \+1–4 per term |
| Crypto | wallet, usdt, bnb, withdraw, deposit, erc20 | \+1–4 per term |
| Pressure | claim, giveaway, limited, congratulations, fastest | \+1–3 per term |

Additional signals: money \+ bonus/withdrawal combos (\+2), crypto wallet addresses (\+3).

If text analysis alone exceeds the threshold, the message is flagged immediately without image processing.

### 2. Image Analysis

If text analysis doesn't reach the threshold, the bot downloads and analyzes attached images using pixel-level feature detection:

- **Dark neon UI detection** — Measures dark pixel ratio, blue/purple balance, and color saturation
- **Green button detection** — Identifies green "claim" or "bonus" action buttons
- **Text-heavy screenshot detection** — Measures bright text pixels and edge density
- **Reference matching** — Compares image features against known casino scam images

Each visual signal contributes 2–3 points, and reference matches add 3–5 points.

## Configuration

- **Threshold** (default: 5) — Minimum score required to trigger detection. Lower values are more sensitive.
- **Actions** — Delete, warn, timeout, kick, ban (configurable order)
- **Alerts** — Toggle alert embeds, set channel, configure ping roles

## Message Triggers

The casino engine only processes messages that contain **image attachments**. Text-only messages are not analyzed by this engine (other engines cover text scams).

## Debug Mode

Set `CASINO_SCAM_DEBUG=true` in the `.env` file to enable verbose logging of image analysis results, including feature ratios and match distances.