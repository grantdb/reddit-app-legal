# User Board

Category: Utility  
Version: v0.0.42  
Visibility: Unlisted  
Summary: Interactive subreddit contributor leaderboard and gamification dashboard.

## Overview
Interactive subreddit contributor leaderboard and gamification dashboard.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/user-board-flowchart.png)

## Key Features
- Not documented yet.

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
- Removes or Filters Content: Yes — Removes or filters non-compliant submissions.
- Dispatches Modmail Alerts: No — Does not send modmail notifications.
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Key patterns: node:http

## Setup and Usage
- Install: Add User Board to your subreddit through the Reddit App Directory.
- Generate Post: Select Create Subreddit User Board from Subreddit Mod Tools.
- Configure Weights: Click  Settings in the top-right corner of the generated post to adjust point multipliers and timeframes.
- Pin: Sticky the generated post to your subreddit to start showcasing top contributors.
- No manual score tallying required. Automated community gamification directly inside Reddit.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.42 — 2026-09-29
- Standard fleet synchronization and maintenance.

0.0.42 — 2026-09-28
- Fix: Fixed moderator verification check by querying `reddit.getModerators({ subredditName })` without unsupported username filtering parameter, eliminating empty moderator listing and false-negative rejection.
- Fix: Replaced single-user negative cache locking with verified moderator list caching (`ub:mod_list_v2:${cleanSub}`).
- Fix: Normalized username and subreddit string matching by stripping leading `u/` and `r/` prefixes.
- Fix: Persisted settings under both `subredditId` and `subredditName` keys for unified lookup.

0.0.41 — 2026-09-29
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/user-board/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/user-board/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/user-board)
- [Support](https://www.reddit.com/r/grantdb)