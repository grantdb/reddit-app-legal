> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/distrofeed-bot)

# DistroFeed Bot

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Content_Automation-8A2BE2?style=for-the-badge)

**DistroFeed Bot** is a manual-only, candidate-scouting and pre-editing curator built for Linux and open-source subreddits. It leverages Google Gemini AI with search grounding to scout major Linux distribution releases and technical updates, allowing moderators to inspect, edit, and post clean, summarized updates.

## Key Features

- **100% Manual & Moderator Control**: Zero auto-posting or background crons. Operates via a 2-stage Mod Menu workflow.
- **AI-Powered Search Grounding**: Uses Google Gemini 2.5 Flash to scan DistroWatch, Phoronix, and 9to5Linux for recent major OS releases and kernel updates.
- **Interactive Pre-Publish Editor**: Presents candidate updates in an interactive Devvit form where moderators can customize post title, target URL, TL;DR summary, post flair, and sticky comment options.
- **Deduplication Engine**: Enforces Redis URL and topic slug tracking to prevent duplicate coverage.

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/DistroFeed-bot-flowchart.png)

1. A moderator opens the Mod Menu and selects **1. Scout Distro Updates** to trigger background AI scanning.
2. After ~90 seconds, the moderator selects **2. Review Scouted Updates** from the Mod Menu.
3. Select an update candidate from the **Candidate Picker Form**.
4. Customize post title, link URL, TL;DR summary, post flair, and sticky comment settings in the **Editor Form**, then click **Publish Post Now**.

## Setup & Configuration

1. **Install**: Add **DistroFeed Bot** to your subreddit via the App Directory.
2. **App Settings**: Navigate to Mod Tools > App Settings > DistroFeed Bot and provide a Google Gemini API Key (from aistudio.google.com).
3. **Usage**: Open the subreddit Mod Menu to scout and review updates.

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/DistroFeed-bot/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/DistroFeed-bot/PRIVACY.md)

---
*Built for Reddit's moderator community.*
