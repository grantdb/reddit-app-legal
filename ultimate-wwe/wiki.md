# Ultimate WWE Hub

Category: Interactive  
Version: v0.1.0  
Visibility: Unlisted  
Summary: Interactive WWE live event mega-thread engine with match cards, pick 'em prediction game, and dual leaderboards.

## Overview
Interactive WWE live event mega-thread engine with match cards, pick 'em prediction game, and dual leaderboards.

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
- Hashes (structured records & alias indices)
- Sorted Sets (time-series audit logs)
- Key patterns: node:http

## Setup and Usage
- Install: Add Ultimate WWE Hub to your subreddit via the Reddit Developer portal or App Directory.
- Launch Thread: From your subreddit menu, select Create WWE Live Event Thread to deploy an official live thread.
- Customize / Lock: Open the post and use Mod Controls to adjust match stipulations or lock predictions at showtime.
- Score & Celebrate: Declare winners as the broadcast unfolds and click Score Event Results to crown community winners!

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.1.0 — 2026-09-15
- Initial release of Ultimate WWE Hub for r/UltimateWWE.
- Devvit 0.14+ Webview Custom Post engine (`wwe-event-live-thread`).
- Reusable event mega-thread template for WWE PLEs, Raw, SmackDown, and NXT.
- Match card scoreboard with championship indicators, match status, and live winner banners.
- Fan prediction game allowing users to pick winners with automatic lock enforcement at bell time.
- Redis-backed event leaderboard and cumulative all-time subreddit leaderboard using sorted sets.
- Moderator tools for spawning threads, manually locking predictions, and scoring results.
- Dedicated live-comments callout banner reminding fans to sort by "New / Live".

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/ultimate-wwe/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/ultimate-wwe/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/ultimate-wwe)
- [Support](https://www.reddit.com/r/grantdb)