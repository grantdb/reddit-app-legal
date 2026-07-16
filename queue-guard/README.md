# GuardHub: Queue-Guard 🛡️

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Hardened-red?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blueviolet?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Monitoring-8A2BE2?style=for-the-badge)

**Queue-Guard** is an advanced, non-destructive decision support layer designed specifically to assist human moderators in the triage queue. Instead of blindly automating removals, it surfaces critical context—like hidden duplicate posts, evasive account signals, and prior moderator actions—directly onto posts, empowering your team to make faster, safer, and more informed queue decisions.

## Key Features

- **Duplicate Detection**: Automatically scans your recent subreddit history to see if the author has submitted highly similar or duplicate content recently, highlighting potential spam rings.
- **Account Signals**: Visually flags new accounts, accounts with drastically low karma, or accounts currently in a suspended state, drawing attention to high-risk actors.
- **Prior Mod Context**: Alerts you to recent removals, bans, or moderator notes applied to the user, ensuring your team has full historical context before approving a post.
- **Queue Guard Dashboard**: A dedicated, secure view to see all recent triage reports at a glance, making queue processing highly efficient.
- **Automated Mod Notes**: Can optionally drop a summary Mod Note on flagged items to ensure transparent tracking for the rest of the moderation team.

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/queue-guard-flowchart.png)

1. A moderator is reviewing a suspicious post in the modqueue.
2. They trigger Queue-Guard by selecting "View Queue-Guard Summary" from the post's overflow menu.
3. The app instantly aggregates data from the user's profile, recent subreddit history, and internal mod logs.
4. A highly readable triage report is presented to the moderator highlighting any risks (e.g., "User had a post removed yesterday", "Account is 2 days old").

## Setup & Configuration

1. **Install**: Add **Queue-Guard** to your subreddit via the App Directory.
2. **Dashboard Initialization**: Open the Queue-Guard Settings page from your subreddit's app settings to configure your flagging policies and risk thresholds.
3. **Usage**: Access Queue-Guard triage reports directly from any post's overflow menu via the native "View Queue-Guard Summary" action.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/queue-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/queue-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
