# Ring Escape: Serpent Flagship

Category: Interactive  
Version: v0.0.69  
Visibility: Unlisted  
Summary: Stealth infiltration game. Sabotage four systems aboard a Serpent Empire warship and escape through the rings.

## Overview
Stealth infiltration game. Sabotage four systems aboard a Serpent Empire warship and escape through the rings.

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
- Removes or Filters Content: No — Does not remove or filter content.
- Dispatches Modmail Alerts: No — Does not send modmail notifications.
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Sorted Sets (time-series audit logs)
- Key patterns: node:http

## Setup and Usage
- Install: Add Ring Escape to your subreddit via the Reddit App Directory.
- Launch Post: Open the Mod Menu anywhere in your subreddit and select "Create Ring Escape Post"**.
- Engage Community: Members click "Play Mission"** inline to launch the expanded gameplay canvas.
- Track Rivalries: High scores and ranks update automatically on the post's live leaderboard.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.69 — 2026-10-03
- Standard fleet synchronization and maintenance.

0.0.68 — 2026-09-21
- Standard fleet synchronization and maintenance.

0.0.67 — 2026-09-15
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/ring-escape/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/ring-escape/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/ring-escape)
- [Support](https://www.reddit.com/r/grantdb)