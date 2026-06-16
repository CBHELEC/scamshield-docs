---
title: "Self-Hosting"
description: "Running your own instance of ScamShield."
icon: "server"
---

# Self-Hosting

ScamShield is open-source and can be self-hosted. This guide covers setting up your own instance.

## Requirements

- Python 3.10+
- Discord Bot Token
- Discord OAuth2 Application (for dashboard)
- (Optional) Tesseract OCR for image text extraction

## Repository

```
git clone https://github.com/anomalyco/UniversalAntiScam
cd UniversalAntiScam
```

## Configuration

### 1. Create a Discord Application

1. Go to the [Discord Developer Portal](https://discord.com/developers/applications)
2. Create a new application
3. Go to the **Bot** section and create a bot
4. Enable **Message Content Intent** under Privileged Gateway Intents
5. Copy the bot token
6. Go to **OAuth2** and copy the Client ID and Client Secret
7. Add a redirect URL: `http://localhost:9000/callback`

### 2. Set Up Environment Variables

Copy the `.env.example` to `.env` and fill in your values:

| Variable | Description |
|---|---|
| `BOT_TOKEN` | Discord bot token |
| `DISCORD_CLIENT_ID` | OAuth2 client ID |
| `DISCORD_CLIENT_SECRET` | OAuth2 client secret |
| `SESSION_SECRET` | Random string for session encryption |
| `IPC_SECRET` | Shared secret for bot-dashboard IPC |
| `DEV_IDS` | Comma-separated Discord user IDs for developer commands |

### 3. Install Dependencies

```
pip install -r requirements.txt
```

### 4. Run the Bot

```
python bot.py
```

### 5. Run the Dashboard (Optional)

```
python dashboard.py
```

## Image Analysis Requirements

For casino scam image analysis, Pillow is required:

```
pip install Pillow
```

For OCR text extraction from images (used by `/check`):

```
# Install Tesseract OCR system package
# Ubuntu/Debian: sudo apt install tesseract-ocr
# Windows: Download from https://github.com/UB-Mannheim/tesseract/wiki

pip install pytesseract
```

## Developer Commands

Developer-only commands (`/dev status`, `/dev sync`, `/dev reload`, etc.) are restricted to:
- The bot owner (user who created the application)
- Users listed in the `DEV_IDS` environment variable

## Database

The bot uses SQLite via SQLAlchemy. The database file is created automatically at `data/uas.db`. No external database setup is required.
