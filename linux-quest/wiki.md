> [Full User Guide](https://www.reddit.com/r/grantdb/wiki/linux-quest/) | **Technical Reference & Settings Spec**

# Linux Quest

Category: Community  
Version: v0.0.135  
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
- Key patterns: node:test, leaderboard:t3_1, node:http

## Setup and Usage
- Install: Add Linux Quest to your subreddit from the Reddit App Directory.
- Create a Post: Open your subreddit's moderator menu and click Create Linux Quest Post.
- Share with Members: Pin the post or link to it in your subreddit sidebar, rules, or help wiki so new users can practice before opening a support thread.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.135 — 2026-11-21
- Add top-bar Rankings button to view live post leaderboard at any time, move Leaderboard prominently above Support Brief on BootResult and always render it, and always refresh leaderboard on completion

0.0.134 — 2026-11-20
- Everyday hardware roster (Old Laptop, Everyday PC, Midrange Gaming PC, Aging Pre-2012 Laptop), popular distros (Linux Mint 22, Pop!_OS 24.04, Fedora 41, EndeavourOS), real-life USB flashing flow (drive/tool/FAT32-exFAT-NTFS), persistent ContextSummaryBanner with hints, distro-accurate filesystems (Btrfs/ext4/FAT32), and streamlined Username+Password account setup without Hostname/Localization

0.0.133 — 2026-11-19
- Fix Redis TxClient zScore NaN bug preventing leaderboard saves (with WATCH conflict retry & unit tests), add NEW PERSONAL BEST & current-user Leaderboard highlight, and de-cramp UI with full-bleed mobile shell, top progress bar, grouped SystemSetup cards, and wider responsive grids

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/linux-quest/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/linux-quest/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/linux-quest)
- [Support](https://www.reddit.com/r/grantdb)