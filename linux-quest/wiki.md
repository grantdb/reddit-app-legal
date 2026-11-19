> [Full User Guide](https://www.reddit.com/r/grantdb/wiki/linux-quest/) | **Technical Reference & Settings Spec**

# Linux Quest

Category: Community  
Version: v0.0.132  
Visibility: Public  
Summary: Industrial OS simulator. Refactored architecture for direct webview rendering. Hardened state machine.

## Overview
Industrial OS simulator. Refactored architecture for direct webview rendering. Hardened state machine.

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
- Install: Add Linux Quest to your subreddit from the Reddit App Directory.
- Create a Post: Open your subreddit's moderator menu and click Create Linux Quest Post.
- Share with Members: Pin the post or link to it in your subreddit sidebar, rules, or help wiki so new users can practice before opening a support thread.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.132 — 2026-11-19
- Fix Partitioning back-navigation lockout, server HTTP 400/session handling & stack leak, stage counter & breadcrumb state, React 19 timers/updaters, unify end-to-end boot/troubleshooting scenarios, adopt Canonical Webview v2.1 & render Leaderboard, remove emoji/unused deps, and align README to 3-tier standard

0.0.131 — 2026-11-09
- Devvit SDK v0.15.2 baseline and minor/patch dependency maintenance update.

0.0.130 — 2026-10-27
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/linux-quest/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/linux-quest/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/linux-quest)
- [Support](https://www.reddit.com/r/grantdb)