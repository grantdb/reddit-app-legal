# Ultimate WWE Hub

Category: Interactive  
Version: v0.0.8  
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
0.0.8 — 2026-09-26
- Standard fleet synchronization and maintenance.

0.0.8 — 2026-09-26
- Resolve custom post loading failure by adding canonical entry: default and textFallback to all submitCustomPost endpoints.
- Update PLE calendar to active late 2026 slate: WWE Bad Blood (Oct 3, 2026), Crown Jewel (Nov 7, 2026), and Survivor Series: WarGames (Nov 28, 2026) with automated Redis schedule migration.
- Add defensive null guards and error boundaries across renderUpcomingSchedule and startCountdownTimer.
- Isolate hypeVotes per-user state from shared Redis post storage.
- Align devvit.json entrypoint configuration with single canonical default webview.

0.0.7 — 2026-09-26
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/ultimate-wwe/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/ultimate-wwe/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/ultimate-wwe)
- [Support](https://www.reddit.com/r/grantdb)