# GuardHub: User Guard 🛡️

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Gatekeeper-8A2BE2?style=for-the-badge)

**User Guard** provides high-precision control over who is permitted to participate in your community. It replaces complex AutoModerator karma and age rules with a clear, priority-based identity engine and a clean, native dashboard interface. It allows moderation teams to quickly lock down the subreddit from bad actors while preserving access for trusted members.

## Key Features

- **Identity Gating**: Create exact username allowlists (always permitted) and blocklists (always rejected) that override all other threshold rules.
- **Maturity Thresholds**: Set minimum account age requirements to block day-zero throwaway accounts and ban evaders.
- **Community Reputation**: Enforce subreddit-specific karma thresholds, ensuring users have a proven track record before posting links or creating threads.
- **Safe Testing Mode**: Built-in "Audit Mode" allows you to test strict thresholds in the background, viewing the logs to see who *would* have been blocked, before enforcing the rule live.
- **Private Dashboard**: A fully secure, moderator-only Custom Post Dashboard for managing access rules without touching code.

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/user-guard-flowchart.png)

1. A user attempts to submit a post or comment in the community.
2. User Guard intercepts the event and checks the author against explicit Identity Gates (allowlists/blocklists).
3. If not explicitly allowed or blocked, it checks the user's account age and karma against your configured thresholds.
4. If a threshold is failed, the content is removed (or just logged, if in Audit Mode) and a report is generated for the moderation team.

## Setup & Configuration

1. **Install**: Add **User Guard** to your subreddit via the App Directory.
2. **Dashboard Initialization**: Navigate to your subreddit's Mod Tools and open the GuardHub: User Guard Dashboard.
3. **Configure Rules**: 
   - Navigate to the Rules tab to create your first threshold (e.g., "Block New Accounts < 7 days").
   - We recommend running new thresholds in Audit Mode first.
4. **Monitoring**: Review access rejections in the Dashboard logs to adjust rule sensitivity over time.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/user-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/user-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
