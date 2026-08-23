# Linux Quest

Category: Community  
Version: v0.0.122  
Visibility: Public  
Summary: Industrial OS simulator. Refactored architecture for direct webview rendering. Hardened state machine.

## Overview
Industrial OS simulator. Refactored architecture for direct webview rendering. Hardened state machine.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/linux-quest-flowchart.png)

## Key Features
- Context-Aware Scenarios: Features engaging, interactive simulations covering common issues like installations, hardware compatibility, and terminal troubleshooting.
- Support Readiness Brief: Upon completing the quest, the game generates a formatted, shareable summary including the user's system context and attempted fixes, ready to be pasted into a real support thread.
- Behavioral Scoring: Measures and rewards support-readiness behavior (precision, clarity, providing logs) rather than expecting the user to know technical trivia.
- Interactive Onboarding: Clear mission objectives displayed natively on startup to hook users immediately.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- AppInstall: Delivered by Reddit event router to endpoint /internal/on-app-install.

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- No custom app settings.

## Automation Capabilities
- Submits Automated Comments: No — Does not submit automated comments.
- Attaches Removal Notes: No — Does not attach removal notes.
- Approves Content: No — Does not approve content.
- Removes or Filters Content: No — Does not remove or filter content.
- Dispatches Modmail Alerts: No — Does not send modmail notifications.
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Sorted Sets (time-series audit logs)
- Key patterns: node:http, node:events

## Setup and Usage
- Install: Add Linux Quest to your subreddit via the App Directory.
- Dashboard Initialization: Navigate to your subreddit's Mod Tools and open the Linux Quest configuration post if you wish to tweak settings.
- Usage: Users can launch the quest directly from an interactive post in the community. We recommend linking to it from your subreddit's sidebar or rules.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.122 — 2026-08-15
- Standard fleet synchronization and maintenance.

0.0.121 — 2026-07-27
- Verification & Sync: Standardized server error status code handling and Redis ZSET leaderboard query performance.

0.0.120 — 2026-07-24
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/linux-quest/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/linux-quest/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/linux-quest)
- [Support](https://www.reddit.com/r/grantdb)