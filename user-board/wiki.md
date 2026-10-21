# User Board

Category: Utility  
Version: v0.0.48  
Visibility: Public  
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
- Generate Post: In your subreddit mod tools, click Create Subreddit User Board to publish the interactive post.
- Configure Weights: Click Settings in the top-right corner of the generated post to open the Expanded Mode console and adjust multipliers or timeframes.
- Pin: Sticky the generated post to your subreddit to start showcasing top contributors.
- No manual score tallying required. Automated community gamification directly inside Reddit.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.48 — 2026-10-21
- Standard fleet synchronization and maintenance.

0.0.48 — 2026-10-21
- Fix: Added NSFW subreddit detection via `reddit.getSubredditByName` and applied `nsfw: isNsfw` plus `textFallback` in `submitCustomPost` to prevent HTTP 400 rejection when creating board posts in 18+ communities.
- Fix: Updated `/internal/on-app-install` to safely parse incoming request body buffer for `subredditId` and `subredditName` rather than falling back to global context.
- Hardening: Wrapped aggregation post batch fetching in error boundary logging to diagnose Reddit API query failures gracefully.
- Architecture: Overhauled inline feed view (`webviews/index.html`) to implement the `pinned-menuboard` 4-item button pagination standard (`◀ Prev` / `Next ▶`, zero scroll trap, bounded 512px max-height, mobile <=360px budget).
- Architecture: Migrated deep 30-rank leaderboard and moderator settings console into Expanded Mode (`requestExpandedMode`), eliminating modal scroll traps from feed view.
- UX: Implemented 8px swipe-drag threshold guard on interactive elements to prevent accidental button activation during feed scrolling.

0.0.47 — 2026-10-20
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/user-board/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/user-board/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/user-board)
- [Support](https://www.reddit.com/r/grantdb)