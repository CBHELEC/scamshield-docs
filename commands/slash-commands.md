---
title: "Slash Commands"
description: "Complete reference of all ScamShield slash commands."
icon: "slash"
---

# Slash Commands

## /help

Show an interactive help panel with all available commands organized by category.

**Usage:** `/help`

The response includes a dropdown menu to browse command categories. Only the user who invoked the command can interact with the menu.

## /ping

Check the bot's connection latency.

**Usage:** `/ping`

**Response:** `Pong! 42ms`

## /check

Manually analyse a message or image for scam patterns.

**Usage:** `/check text: <text> image: <attachment>`

**Parameters:**
- `text` (optional) — The message text to analyse
- `image` (optional) — An image to scan (OCR text extraction)

**Response:** Ephemeral embed with risk level, probability, and matched patterns.

At least one parameter must be provided.

## /warns

View the warning history for a user.

**Usage:** `/warns user: @username`

**Parameters:**
- `user` (required) — The user to look up

**Response:** Ephemeral embed showing total warnings and up to 10 most recent entries with timestamps, reasons, and moderators.

## /history

View the scam detection history for a user.

**Usage:** `/history user: @username`

**Parameters:**
- `user` (required) — The user to look up

**Response:** Ephemeral embed showing total detections and up to 10 most recent entries with type, score, confidence, and action taken.

## /config

Get a link to the web dashboard for server configuration.

**Usage:** `/config`

**Response:** Ephemeral embed with the dashboard URL.

## /dev status

Change the bot's custom status (developers only).

**Usage:** `/dev status new_status: <text>`

## /dev sync

Sync all global slash commands (developers only).

**Usage:** `/dev sync`

## /dev reload

Reload one or all cogs without restarting the bot (developers only).

**Usage:** `/dev reload target: <cog name>`

**Parameters:**
- `target` (optional) — Cog name to reload. Leave empty to reload all.

## /dev clear-cmds

Clear and re-register all global commands (developers only).

**Usage:** `/dev clear-cmds`

## /dev uptime

Show how long the bot has been running.

**Usage:** `/dev uptime`

**Response:** Bot uptime in `HH:MM:SS` format.
