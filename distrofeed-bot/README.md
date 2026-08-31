> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/distrofeed-bot)

# DistroFeed Bot

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Content_Automation-8A2BE2?style=for-the-badge)

> **Manual-only Linux release curation and candidate scouting engine for Reddit moderators.**

**DistroFeed Bot** is a manual-only candidate-scouting and pre-editing curator built for Linux and open-source subreddits. It leverages Google Gemini AI with search grounding to scout major Linux distribution releases and technical updates, allowing moderators to inspect, edit, and post clean, summarized community updates.

---

## Key Features

- **100% Manual & Moderator Control**: Zero auto-posting or background crons. Operates via an interactive Mod Menu popout workflow.
- **AI-Powered Search Grounding**: Uses Google Gemini 2.5 Flash to scan DistroWatch, Phoronix, and 9to5Linux for recent major OS releases and kernel updates.
- **Interactive Pre-Publish Editor**: Presents candidate updates in an interactive Devvit form where moderators can customize post title, target URL, TL;DR summary, post flair, and sticky comment options.
- **Unified Menu Popout**: Access both scouting and candidate review flows from a single **DistroFeed Bot** menu item.
- **Deduplication Engine**: Enforces Redis URL and topic slug tracking to prevent duplicate coverage.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/DistroFeed-bot-flowchart.png)

### Your Four-Step Workflow

1. **Scout Updates**: Open the subreddit menu (`...`), select **DistroFeed Bot**, and choose **1. Scout Updates** to trigger background AI scanning.
2. **Review Candidates**: After ~90 seconds, open **DistroFeed Bot** and choose **2. Review & Publish**.
3. **Pick Update**: Select an update candidate from the interactive Candidate Picker Form.
4. **Customize & Publish**: Review and customize post title, link URL, TL;DR summary, post flair, and sticky comment settings, then click **Publish Post Now**.

---

## Setup & Configuration

1. **Install**: Add **DistroFeed Bot** to your subreddit via the App Directory.
2. **App Settings**: Navigate to **Mod Tools > App Settings > DistroFeed Bot** and provide a Google Gemini API Key (from aistudio.google.com).
3. **Usage**: Open the subreddit menu (`...`), click **DistroFeed Bot**, and scout or review updates on your schedule.

---

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

---

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/DistroFeed-bot/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/DistroFeed-bot/PRIVACY.md)

---
*Built for Reddit's moderator community.*
