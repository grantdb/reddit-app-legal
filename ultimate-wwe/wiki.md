# Ultimate WWE Hub

Category: Interactive  
Version: v0.0.15  
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
- Launch Pinned Hub Posts: From your subreddit menu (`...`), deploy the Superstar Stats & Records Post, Championship Belts & Leaderboard Post, and Upcoming Matches & Schedule Post as pinned community anchors.
- Deploy Live Event Thread: On event night, select Create WWE Live Event Thread to launch the show mega-thread.
- Score & Crown Champions: Declare winners as the broadcast unfolds and click Score Event & Defend Belts to crown champions and update community rankings!

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.15 — 2026-10-07
- Standard fleet synchronization and maintenance.
- All notable changes to the Ultimate WWE Hub application will be documented in this file.

0.0.14 — 2026-10-07
- Standard fleet synchronization and maintenance.

0.0.13 — 2026-10-05
- Fix infinite Redis schedule overwrite loop by replacing expired countdown auto-heal logic with clean one-time legacy migration.
- Roll forward authoritative WWE calendar defaults to Crown Jewel 2026 (Nov 7), Survivor Series: WarGames 2026 (Nov 28), Saturday Night's Main Event (Dec 12), and Royal Rumble 2027 (Jan 30).
- Implement full Live Event Match Card Manager: edit match title, stipulation, participants, championship stakes, points value, add surprise matches, and delete matches.
- Implement full Upcoming Shows & Fight Card Manager: select and edit show metadata (event name, show type, date text, venue, network, countdown target datetime picker), add new shows, delete shows, add announced matches, edit match details, delete matches, and reset to WWE defaults.
- Add `/api/schedule/update` server endpoint guarded with moderator verification.
- Add modal dialogs for live event and scheduled match editing with zero scroll trap interference.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/ultimate-wwe/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/ultimate-wwe/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/ultimate-wwe)
- [Support](https://www.reddit.com/r/grantdb)