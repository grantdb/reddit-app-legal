# User Board

Category: Utility  
Version: v0.0.45  
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
- Generate Post: Select Create Subreddit User Board from Subreddit Mod Tools.
- Configure Weights: Click  Settings in the top-right corner of the generated post to adjust point multipliers and timeframes.
- Pin: Sticky the generated post to your subreddit to start showcasing top contributors.
- No manual score tallying required. Automated community gamification directly inside Reddit.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.45 — 2026-10-07
- Standard fleet synchronization and maintenance.

0.0.44 — 2026-10-02
- Standard fleet synchronization and maintenance.

0.0.44 — 2026-10-02
- Feature: Completely overhauled scoring engine to reward positive community engagement and quality over raw post spam.
- Feature: Added comment tree ingestion (`reddit.getComments`) to index commenters, comment upvote scores, and discussion thread depth (`repliesReceived`).
- Feature: Rewrote scoring formula to reward post upvotes (3x), comment upvotes (2x), discussion spark (2x), and thread replies (1x) over baseline volume.
- Feature: Added contributor classification badges: Top Poster, Commenter, Engager, Consistent, and Rising Star.
- Feature: Expanded Moderator Console settings with granular Quality & Reception weights and quick "Defaults" restore.
- UI: Added post count, comment count, and total upvotes received columns to the interactive leaderboard table.
- Compatibility: Maintained full backward compatibility with legacy snapshots, fallback aliases, and default settings merging.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/user-board/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/user-board/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/user-board)
- [Support](https://www.reddit.com/r/grantdb)