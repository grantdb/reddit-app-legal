# Ultimate WWE Hub

Category: Interactive  
Version: v0.0.2  
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
- Launch Pinned Hub Posts: From your subreddit menu (`...`), deploy the Championship Belts & Leaderboard Post and Upcoming Matches & Schedule Post as pinned community anchors.
- Deploy Live Event Thread: On event night, select Create WWE Live Event Thread to launch the show mega-thread.
- Score & Crown Champions: Declare winners as the broadcast unfolds and click Score Event & Defend Belts to crown champions and update community rankings!

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.2 — 2026-09-20
- Standard fleet synchronization and maintenance.
- All notable changes to the Ultimate WWE Hub application will be documented in this file.

0.2.0 — 2026-09-20
- Expanded Ultimate WWE Hub into a multi-post ecosystem with 3 dedicated custom post types:
- Live Event & Prediction Mega-Threads
- Community Championship Belts Trophy Case & All-Time Leaderboards
- Upcoming Matches & PLE Schedule Hub
- Implemented Community Championship Belts Engine featuring World Heavyweight, Intercontinental, PLE Cup, 24/7 Hardcore, and Women's World Championship titles with automated title defense and transfers on event scoring.
- Added Live PLE Countdown Timer with millisecond precision and weekly broadcast schedule guide (Raw on Netflix, SmackDown on USA, NXT on CW).
- Added Community Hype Voting Meter for upcoming fight cards and shows.
- Added cross-post navigation hub banner connecting all community posts.
- Implemented canonical horizontal top-bar navigation scrolling (◀ and ▶) with 48px fine-tuned steps, continuous long-press acceleration, and visible high-contrast scrollbars.
- Added moderator controls to manually award championship belts to community members.

0.1.0 — 2026-09-17
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