# Ultimate WWE Hub

Category: Interactive  
Version: v0.0.21  
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
- Launch Pinned Hub Posts: From your subreddit menu (`...`), deploy the Superstar Stats, Records & Belts Post and Community Prediction & Picking Board as pinned community anchors.
- Deploy Live Event Thread: On event night, select Create WWE Live Event Thread to launch the show mega-thread with live match cards, community pick consensus, and live chat.
- Score & Crown Champions: Declare winners as the broadcast unfolds and click Score Event Results to update community rankings!

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.21 — 2026-10-16
- Standard fleet synchronization and maintenance.

0.0.21 — 2026-10-15
- Feed Mode Standard: Implemented compact 512px tall `#inline-launchpad` with featured main event preview, consensus bar, countdown timer, and primary "ENTER WWE ARENA (EXPANDED MODE)" launch CTA button conforming to mod360pro canonical standard.
- Main Nights Auto-Setup Engine: Added 1-click presets for Monday Night Raw, WWE NXT Tuesday, Friday Night SmackDown, and upcoming PLEs with dynamic next-broadcast countdown targets.
- Quick Match Builder: Added 1-tap roster chip picker covering authoritative 2026 WWE superstars with quick template pills (Singles, Title Match, Tag Team, Triple Threat) eliminating manual text typing friction.
- Automated Win/Loss Tracking & 2026 Baseline Recalibration: Built-in match completion and scoring engine automatically updates superstar season records, streaks, and title defense milestones directly in Redis without external API dependencies.
- Zero-Fetch Architecture: Operates entirely self-contained within Devvit, Redis, and Reddit native permissions, omitting HTTP fetch domains to ensure instantaneous updates and zero admin review queue delays.

0.0.20 — 2026-10-10
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/ultimate-wwe/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/ultimate-wwe/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/ultimate-wwe)
- [Support](https://www.reddit.com/r/grantdb)