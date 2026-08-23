> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/canucknews-bot)

# Canuck News Bot

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-News-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Content_Curation-8A2BE2?style=for-the-badge)

**Canuck News Bot** is a manual-only, candidate-scouting and pre-editing tool designed to deliver curated, balanced, and non-political news from across Canada directly to your subreddit. It operates with zero automated posting—moderators scout, review, edit, and confirm every candidate story before publishing.

## Key Features

- **100% Manual & Moderator Control**: Operates strictly on-demand. The bot will never auto-post or run background crons.
- **Candidate Scouting Pipeline**: Interactively scans CBC, Global News, and Globe & Mail feeds based on your selected subject focus (Health, Science, Tech, Business, Lifestyle, Regional).
- **Pre-Publish Editor**: Presents candidate stories in an interactive Devvit form allowing moderators to inspect and customize the post title, link URL, flair, and spoiler settings before publishing.
- **Content & Spam Filtering**: Automatically filters out political content and controversial topics to maintain a neutral community environment.
- **30-Day Redis Deduplication**: Prevents duplicate link submissions across all scouting runs.

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/CanuckNews-bot-flowchart.png)

1. A moderator opens the subreddit Mod Menu and launches **Scout Canadian News**.
2. Select candidate pool size and subject filters in the **Scout Form**.
3. Inspect scouted candidate articles in the **Candidate Picker Form** and select a story.
4. Customize the post title, flair ID, and spoiler settings in the **Editor Form**, then click **Publish Post Now**.

## Setup & Configuration

1. **Install**: Add **Canuck News Bot** to your subreddit via the App Directory.
2. **App Settings**: Navigate to Mod Tools > App Settings > Canuck News Bot to map optional regional post flair IDs.
3. **Usage**: Open the subreddit Mod Menu and click **Scout Canadian News** to begin scouting.

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/CanuckNews-bot/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/CanuckNews-bot/PRIVACY.md)

---
*Built for Reddit's moderator community.*
