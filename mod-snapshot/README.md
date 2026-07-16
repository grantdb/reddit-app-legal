# Mod Snapshot

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Archival](https://img.shields.io/badge/Focus-Archival_Storage-blue?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Secured-success?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Backup-8A2BE2?style=for-the-badge)

**Mod Snapshot** is an essential disaster-recovery and auditing tool for subreddit moderators. It generates a comprehensive, text-based archival record of your subreddit's entire configuration and delivers it directly to your Modmail for secure storage. If a rogue moderator or a compromised account ever wipes your settings, you will have a complete, readable backup to restore from.

## Key Features

- **Comprehensive Data Collection**: Captures everything that matters: Subreddit Settings, Rules, Removal Reasons, Flair Templates, and Appearance configurations.
- **Surgical Extraction**: Retrieves your full AutoModerator YAML configuration. This is crucial for offline backup, team auditing, or transferring complex logic to a sister subreddit.
- **Logical Modmail Delivery**: Intelligently splits large snapshots into multiple sequential Modmail discussions to bypass Reddit's platform character limits, ensuring no data is ever truncated.
- **Moderator-Only Access**: Snapshot triggers and operations are strictly restricted to the Subreddit Mod Tools menu to ensure data security and prevent unauthorized polling.

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/mod-snapshot-flowchart.png)

1. A moderator initiates a manual snapshot from the Mod Tools menu.
2. The app uses the Reddit API to systematically read all crucial configuration layers of the subreddit.
3. The raw data is compiled into a highly readable, Markdown-formatted text document.
4. The chunking engine ensures the document fits within Modmail limits, splitting it logically if necessary, and dispatches it to the moderation team's inbox for safekeeping.

## Setup & Configuration

1. **Install**: Add **Mod Snapshot** to your subreddit via the App Directory.
2. **App Settings**: Open your subreddit's App Settings for Mod Snapshot to adjust your daily manual snapshot limits (prevents accidental spamming).
3. **Usage**: Trigger a fresh snapshot anytime by selecting the action from the Subreddit Mod Tools menu. The backup will arrive in Modmail within seconds.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/mod-snapshot/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/mod-snapshot/PRIVACY.md)

---
*Built for Reddit's moderator community.*
