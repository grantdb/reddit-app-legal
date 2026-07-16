# DistroFeed Bot

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Content_Automation-8A2BE2?style=for-the-badge)

**DistroFeed Bot** is an automated news curator built for Linux and open-source subreddits. It monitors top distribution news sources and automatically shares major releases and updates with the community, ensuring your members never miss an important OS update or security patch.

## Key Features

- **Smart Summaries**: Leverages AI to securely browse news sites and distill long articles into concise, highly readable summaries.
- **Deduplication Engine**: Tracks article hashes and URLs to ensure no story is ever double-posted across manual fetches or scheduled automated runs.
- **Auto-Flairing**: Uses intelligent keyword detection to properly tag posts by distribution (e.g., Arch, Fedora, Ubuntu, Mint), keeping the subreddit cleanly organized.
- **Scheduled or Manual**: Supports automated daily posting via a cron schedule, or on-demand manual fetching when breaking news happens.

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/DistroFeed-bot-flowchart.png)

1. The bot wakes up automatically (daily schedule) or is manually triggered by a moderator.
2. It fetches RSS feeds from authorized Linux news sources.
3. The AI engine reads the articles, creates a short summary, and determines the primary distribution topic.
4. The bot checks its history to prevent duplicates, applies the correct post flair, and submits the post.

## Setup & Configuration

1. **Install**: Add **DistroFeed Bot** to your subreddit via the App Directory.
2. **App Settings**: Navigate to your subreddit's Mod Tools > App Settings > DistroFeed Bot.
3. **Configure**:
   - Enable or disable the daily automated schedule.
   - Map specific keywords to your subreddit's existing flairs (e.g., "Ubuntu" -> template_id).
4. **Manual Fetch**: At any time, use the native Mod Menu action "Post Top Distro Updates" to manually pull in the latest stories.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/DistroFeed-bot/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/DistroFeed-bot/PRIVACY.md)

---
*Built for Reddit's moderator community.*
