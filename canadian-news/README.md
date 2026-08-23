> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/canadian-news)

# Canadian News App

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![News](https://img.shields.io/badge/Category-Regional_News-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Content_Curation-8A2BE2?style=for-the-badge)

**Canadian News App** is a manual-only, candidate-scouting and pre-editing tool designed to deliver highly curated news from across Canada directly to your subreddit. It operates with zero background automation—moderators scout, review, edit, and approve every post before it hits the live feed.

## Key Features

- **100% Manual Moderator Control**: Zero auto-posting or background crons. You decide when news is scouted and published.
- **Multi-Subject Scouting**: Scout stories across Politics, Health, Science, Technology, Crime, Business, Lifestyle, or Regional news feeds.
- **Pre-Publish Editor**: Review scouted candidate stories in an interactive Devvit form to customize the post title, target URL, and spoiler tags prior to posting.
- **Spam Filtering & Deduplication**: Automatically filters promotional and spam content while enforcing 30-day link deduplication in Redis.

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/canadian-news-flowchart.png)

1. A moderator opens the subreddit Mod Menu and clicks **Scout Canadian News**.
2. Configure candidate pool size and subject filters in the **Scout Parameter Form**.
3. Select a candidate article from the **Candidate Picker Form**.
4. Fine-tune the post title, target URL, and spoiler settings in the **Editor Form**, then click **Publish Post Now**.

## Setup & Configuration

1. **Install**: Add **Canadian News App** to your subreddit via the App Directory.
2. **Usage**: Open the subreddit Mod Menu and click **Scout Canadian News** to launch the interactive scouting workflow.

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/canadian-news/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/canadian-news/PRIVACY.md)

---
*Built for Reddit's moderator community.*
