> [Full User Guide](https://www.reddit.com/r/grantdb/wiki/rescue-guard/) | **Technical Reference & Settings Spec**

# RescueGuard

Category: Moderation  
Version: v0.0.28  
Visibility: Unlisted  
Summary: Subreddit post-discovery & manual spotlight moderation engine for Reddit.

## Overview
Subreddit post-discovery & manual spotlight moderation engine for Reddit.

## Key Features
- Not documented yet.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- Not documented yet.

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- No custom app settings.

## Automation Capabilities
- Submits Automated Comments: Yes — Posts automated comments on target submissions.
- Attaches Removal Notes: No — Does not attach removal notes.
- Approves Content: Yes — Approves content.
- Removes or Filters Content: Yes — Removes or filters non-compliant submissions.
- Dispatches Modmail Alerts: No — Does not send modmail notifications.
- Updates User or Post Flair: Yes — Updates post or user flair based on rules.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Key patterns: node:http

## Setup and Usage
- Install: Add RescueGuard to your subreddit through the Reddit App Directory.
- Launch Review: Open the subreddit menu and select GuardHub: RescueGuard Review Hub.
- Configure: Open the Settings tab inside the Review Hub dashboard to set your batch size, minimum post age, lookback days, deduplication strategy, and spotlight flair/comment text.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.28 — 2026-11-16
- Enforce moderator auth & cross-subreddit check on /api/*, add null-post guard, sanitize settings, batch scanner Redis lookups, and align README/version

0.0.27 — 2026-11-09
- Devvit SDK v0.15.2 baseline and minor/patch dependency maintenance update.

0.0.26 — 2026-10-27
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/rescue-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/rescue-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/rescue-guard)
- [Support](https://www.reddit.com/r/grantdb)