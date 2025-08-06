# StalkerEyesBot

A Telegram bot that automatically monitors messages in selected groups, marks them as read, and adds customizable reactions after a delay.

## Features

- 🔍 **Group Monitoring**: Automatically monitor messages in selected Telegram groups/channels
- ✅ **Auto-Read**: Instantly marks messages as read when they arrive
- 👀 **Delayed Reactions**: Adds customizable reactions to messages after 2 minutes
- 🎯 **Multiple Reactions**: Choose from 10 different reaction types per group
- 📱 **User-Friendly Interface**: Simple bot interface with inline keyboards
- 🔄 **Auto-Reconnect**: Handles connection issues gracefully
- 📊 **Monitoring Dashboard**: View and manage all active monitors
- 🔐 **Private Bot**: Restricted to owner access only

## Available Reactions

- 👀 Eyes (default)
- 👍 Like
- ❤️ Heart
- 🔥 Fire
- 🎉 Party
- 😁 Smile
- 😮 Surprise
- 😢 Sad
- 🤔 Thinking
- 👎 Dislike

## Prerequisites

- Python 3.7+
- Telegram API credentials (API ID and API Hash)
- Telegram Bot Token from [@BotFather](https://t.me/botfather)

## Installation

1. Clone the repository:
```bash
git clone https://github.com/newzealandgrom/StalkerEyesBot.git
cd StalkerEyesBot
```

2. Install dependencies:
```bash
pip install telethon
```

3. Configure the bot:
   - Open `bot.py` or `bot_improved.py`
   - Replace the following values with your own:
     ```python
     API_ID = "your_api_id"
     API_HASH = "your_api_hash"
     BOT_TOKEN = "your_bot_token"
     ```

## Usage

1. Start the bot:
```bash
python bot_improved.py
```

2. On first run, you'll need to authenticate with your phone number

3. Open Telegram and start a conversation with your bot

4. Use the bot commands:
   - `/start` - Show main menu
   - 📋 **List Groups** - View all available groups
   - 🔍 **Search Groups** - Search groups by name
   - 🔍 **Active Monitors** - View currently monitored groups
   - 🔄 **Check Availability** - Validate monitored groups
   - ❓ **Help** - Show help information

## How It Works

1. **Group Selection**: Browse or search for groups you want to monitor
2. **Enable Monitoring**: Click on a group to enable monitoring
3. **Choose Reaction**: Click ⚙️ to select a custom reaction for each group
4. **Automatic Processing**:
   - Messages are marked as read immediately
   - After 2 minutes, the selected reaction is added
   - Only processes messages from other users (not your own)

## File Structure

```
StalkerEyesBot/
├── bot.py                 # Original bot implementation
├── bot_improved.py        # Enhanced version with reaction selection
├── monitor_settings.json  # Persistent settings storage
├── user_session.session   # User client session
├── bot_session.session    # Bot client session
├── bot.log               # Rotating log files
├── CLAUDE.md             # Development guide for Claude AI
└── README.md             # This file
```

## Configuration Files

- **monitor_settings.json**: Stores monitored groups and their reaction preferences
- **\*.session**: Telegram session files (do not share these!)
- **bot.log**: Daily rotating log files (keeps last 7 days)

## Security Notes

- The bot is restricted to owner access only
- Session files contain sensitive data - never share them
- API credentials should be kept secret
- Consider using environment variables for credentials in production

## Troubleshooting

### Reactions Not Working
- Check if reactions are enabled in the group
- Verify you still have access to the group
- Run "Check Availability" to validate groups
- Check bot.log for detailed error messages

### Connection Issues
- The bot automatically reconnects on connection loss
- Check your internet connection
- Verify API credentials are correct
- Ensure the bot token is valid

### Authentication Issues
- Delete session files and re-authenticate
- Make sure you're using the correct phone number
- Check if 2FA is enabled on your account

## Development

### Adding New Reactions
To add new reactions, modify the `AVAILABLE_REACTIONS` dictionary in the bot file:
```python
AVAILABLE_REACTIONS = {
    "👀": "Eyes",
    "🆕": "New Reaction",
    # Add more reactions here
}
```

### Logging
The bot uses Python's logging module with daily rotation:
- Info level: General operation logs
- Error level: Issues and exceptions
- Critical level: Unhandled exceptions

## License

This project is provided as-is for educational and personal use.

## Disclaimer

This bot is designed for legitimate use cases such as managing work-related group communications. Users are responsible for complying with Telegram's Terms of Service and respecting privacy in the groups they monitor.

## Contributing

Feel free to submit issues and enhancement requests!

## Support

For issues and questions:
1. Check the logs in `bot.log`
2. Use the in-bot Help command
3. Review the troubleshooting section
4. Open an issue on [GitHub](https://github.com/newzealandgrom/StalkerEyesBot/issues)
