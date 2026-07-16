# SG-1 Responder

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Automation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Community_Engagement-8A2BE2?style=for-the-badge)

**SG-1 Responder** is an automated community engagement utility designed specifically for themed Stargate subreddits. It actively monitors community activity and delivers contextually relevant, flavor-accurate responses to maintain a fun, immersive thematic consistency for fans of the franchise.

## Key Features

- **Contextual Triggers**: Intelligently monitors both new submissions and comment threads for specific franchise-themed keywords and quotes.
- **Automated Interaction**: Automatically delivers canonically accurate responses and character quotes to surprise and engage users.
- **Response Variety**: Utilizes a weighted random selection algorithm when multiple responses apply, ensuring that the bot's interactions remain fresh and unpredictable rather than robotic.
- **Safety Filters**: Built with integrated rate limiting, cooldown timers, and moderator exemptions to ensure the bot adds to the fun without ever becoming spammy or annoying.

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/sg1-responder-flowchart.png)

1. A user posts a comment containing a recognizable quote (e.g., "Indeed").
2. The bot intercepts the comment and verifies that it is not currently on cooldown for that specific trigger.
3. If ready, the bot selects a mathematically weighted response from its internal library of lore-accurate replies.
4. The bot replies to the user, driving further engagement and community fun.

## Setup & Configuration

1. **Install**: Add **SG-1 Responder** to your subreddit via the App Directory.
2. **Configuration**: This app currently requires no manual configuration. Its response library and cooldown timers are hardcoded for optimal engagement out of the box.
3. **Usage**: Simply install the app and watch it interact with your community!

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/sg1-responder/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/sg1-responder/PRIVACY.md)

---
*Built for Reddit's moderator community.*
