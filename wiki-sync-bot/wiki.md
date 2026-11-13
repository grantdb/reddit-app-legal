# WikiSync Bot

Category: Utility  
Version: v0.0.33  
Visibility: Unlisted  
Summary: Subreddit wiki synchronization engine for Reddit communities.

## Overview
Subreddit wiki synchronization engine for Reddit communities.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/wiki-sync-bot-flowchart.png)

## Key Features
- Not documented yet.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)
- http: External HTTP Fetch access [Domains: raw.githubusercontent.com]

## Triggers and Activation
### Menu Actions
- WikiSync Bot: Manage wiki documentation synchronization and schemas (Location: subreddit)

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- enable_release_announcements: Enable App Release Announcements (boolean, default: true). Automatically post release notes and changelog announcements to r/grantdb when a public app is updated.

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
- Key patterns: announcement:posted:, announcement:lock:, wikisync:hash:, wikisync:run:lock

## Setup and Usage
- Install: Add WikiSync Bot to your subreddit.
- Configure: Open Mod Tools > App Settings > WikiSync Bot to toggle `enable_release_announcements`.
- Trigger Operations: Open the subreddit `...` menu, select WikiSync Bot, and run incremental sync, single-app sync, force sync, `bot_knowledge` sync, or manual release broadcast.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.33 — 2026-11-13
- Audit fixes and hardening: blocks.triggers manifest sync, writeWikiPage dual-failure propagation, slug validation, fetch timeouts, Redis run lock, batched sync, and unit tests.

0.0.32 — 2026-11-09
- Devvit SDK v0.15.2 baseline and minor/patch dependency maintenance update.

0.0.31 — 2026-11-07
- Added release announcement enrichment guard and unit tests to prevent generic placeholder notes in r/grantdb update posts.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/wiki-sync-bot/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/wiki-sync-bot/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/wiki-sync-bot)
- [Support](https://www.reddit.com/r/grantdb)