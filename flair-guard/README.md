# GuardHub: Flair Guard 🛡️

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Community_Styling-8A2BE2?style=for-the-badge)

**Flair Guard** is an automated moderation engine for the GuardHub ecosystem focused exclusively on managing post and user flairs. Instead of relying on users to correctly categorize their own content, Flair Guard automatically enforces your community's visual organization by dynamically applying flairs based on post content, user history, or signals from other GuardHub apps.

## Key Features

- **Automated Post Flairing**: Automatically categorizes posts based on title keywords, link domains, or body text patterns without relying on AutoModerator.
- **Dynamic User Tracking**: Instantly applies user flairs based on reputation or community standing, making it easy to identify trusted contributors or warn others about repeat offenders.
- **Standardized Management**: Keep your community visually organized and easily searchable with strict, consistent flair enforcement.
- **Cross-App Integration**: Listens to signals from other GuardHub apps (like Filter Guard) to apply temporary flairs (e.g., "Under Review") during automated moderation events.

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/flair-guard-flowchart.png)

1. A new post is created or an event is triggered by another GuardHub app.
2. Flair Guard evaluates the text content and the author's history against your configured rules.
3. If a match is found, the system immediately applies the specified Post Flair or User Flair.
4. The action is logged to the central GuardHub Audit Guard system.

## Setup & Configuration

1. **Install**: Add **Flair Guard** to your subreddit via the App Directory.
2. **Dashboard Initialization**: Navigate to your subreddit's Mod Tools and open the GuardHub: Flair Guard Dashboard.
3. **Configure Rules**: Create conditions (like keyword matches) and map them to the specific template IDs of the flairs in your subreddit.
4. **Monitoring**: Review flair application logs directly within the dashboard.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/flair-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/flair-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
