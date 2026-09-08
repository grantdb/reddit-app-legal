> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/canadian-news)

# Canadian News App

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![News](https://img.shields.io/badge/Category-Regional_News-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Content_Curation-8A2BE2?style=for-the-badge)

**Canadian News App** is a manual-only, candidate-scouting and pre-editing tool designed to deliver highly curated news from across Canada directly to your subreddit. It operates with zero background automation—moderators scout, review, edit, and approve every post before it hits the live feed.

## Key Features

- **100% Manual Moderator Control**: Zero auto-posting or background crons. You decide when news is scouted and published.
- **Optimized Moderator Control Dialog**: Unified moderator menu offering fresh feed scouting, instant review of cached session candidates, and cache management.
- **Multi-Subject Scouting**: Scout stories across Politics, Health, Science, Technology, Business, Lifestyle, or Regional news feeds.
- **Pre-Publish Editor & Regional Flair Support**: Review scouted candidate stories in an interactive Devvit form to customize the post title, target URL, regional post flair, and spoiler tags prior to posting.
- **Spam Filtering & Deduplication**: Automatically filters promotional and spam content while enforcing 30-day link deduplication in Redis.

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/canadian-news-flowchart.png)

1. A moderator opens the subreddit Mod Menu or post overflow menu and clicks **Canadian News**.
2. From the **Moderator Controls**, choose an action:
   - **Scout Canadian News**: Configure candidate pool size and subject filters in the **Scout Parameter Form**.
   - **Review Scouted Articles**: Instantly review cached candidates from your active session without re-fetching feeds.
   - **Reset Scouting Cache**: Clear your session cache to perform a completely fresh discovery scan.
3. Select a candidate article from the **Candidate Picker Form**.
4. Fine-tune the post title, target URL, regional post flair ID, and spoiler settings in the **Editor Form**, then click **Publish Post Now**.

## Setup & Configuration

1. **Install**: Add **Canadian News App** to your subreddit via the App Directory.
2. **Post Flair Configuration (Optional)**:
   - Navigate to **Subreddit Settings** > **Apps** > **Canadian News App**.
   - Under **Post Flair IDs**, enter the flair template IDs for National and provincial feeds (`flair_national`, `flair_bc`, `flair_ab`, etc.).
   - When a story from a matching region is scouted, the app automatically pre-populates its flair in the editor form.
3. **Usage**: Open the subreddit Mod Menu or post menu and click **Canadian News** to launch the interactive scouting workflow.

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/canadian-news/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/canadian-news/PRIVACY.md)

---
*Built for Reddit's moderator community.*
