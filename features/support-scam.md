---
title: "Support Scam Detection"
description: "Detects masked and obfuscated URLs used in Discord support impersonation scams."
icon: "eye-off"
---

# Support Scam Detection

The Support engine detects obfuscated URLs that scammers use to impersonate Discord support. These URLs hide their true destination using various encoding techniques.

## How It Works

The engine applies a series of cleaning techniques to reveal hidden URLs:

### Detection Techniques

1. **Zero-width character stripping** — Removes invisible Unicode characters used to break up URLs
2. **Unicode homoglyph normalization** — Replaces lookalike characters (like Cyrillic letters that resemble Latin) with their ASCII equivalents
3. **URL encoding detection** — Identifies `%XX` encoded characters
4. **Bracket obfuscation** — Detects URLs split with `[` and `]` brackets
5. **Full-width character conversion** — Normalizes full-width Unicode characters

The engine only flags a URL as suspicious if it was **revealed** by the cleaning process — URLs already visible in the raw text are not flagged.

### Common Scam Patterns Detected

- "discord-app.com" lookalikes using Unicode homoglyphs
- Split URLs like `discord.` and `gift/...` using zero-width spaces
- URL-encoded `%68%74%74%70%73` protocol prefixes
- Support impersonation directing victims to fake staff

## Configuration

- **Actions** — Delete, warn, timeout, kick, ban (configurable order)
- **Alerts** — Toggle alert embeds, set channel, configure ping roles

## Message Triggers

This engine analyzes the text content of every message. It is not limited to messages with attachments.
