# User Board

Category: Moderation  
Version: v0.0.34  
Visibility: Public  
Summary: Subreddit top-poster analytics and custom post leaderboard.

## Overview
Subreddit top-poster analytics and custom post leaderboard.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/user-board-flowchart.png)

## Key Features
- Not documented yet.

## Permissions Used
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
- Key patterns: node:http

## Setup and Usage
- Install: Add User Board to your subreddit through the Reddit App Directory.
- Configure Weights: Open Mod Tools > App Settings > User Board to adjust point multipliers.
- Generate Post: Select Create Subreddit User Board from Subreddit Mod Tools.
- Pin: Sticky the generated post to your subreddit to start showcasing top contributors.
- No manual score tallying required. Automated community gamification directly inside Reddit.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.34 — 2026-09-02
- Standard fleet synchronization and maintenance.

0.0.33 — 2026-08-15
- Standard fleet synchronization and maintenance.

0.0.32 — 2026-08-10
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/user-board/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/user-board/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/user-board)
- [Support](https://www.reddit.com/r/grantdb)