> [Full User Guide](https://www.reddit.com/r/grantdb/wiki/gimmecode-guard/) | **Technical Reference & Settings Spec**

# GimmeCode Guard

Category: Moderation  
Version: v0.0.52  
Visibility: Unlisted  
Summary: Detects low-effort give me code requests

## Overview
Detects low-effort give me code requests

## Key Features
- High-Precision Moderation Rules: Dynamic pattern matching and content enforcement.
- Idempotency: Powered by `devvit-utils` TaskRunner to guarantee exact-once execution and zero-drift state sync.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- CommentSubmit: Delivered by Reddit event router to endpoint /internal/trigger/comment-submit.
- CommentDelete: Delivered by Reddit event router to endpoint /internal/trigger/comment-delete.

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- No custom app settings.

## Automation Capabilities
- Submits Automated Comments: Yes — Posts automated comments on target submissions.
- Attaches Removal Notes: No — Does not attach removal notes.
- Approves Content: No — Does not approve content.
- Removes or Filters Content: Yes — Removes or filters non-compliant submissions.
- Dispatches Modmail Alerts: Yes — Sends modmail notifications.
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Hashes (structured records & alias indices)
- Sorted Sets (time-series audit logs)
- Key patterns: node:http, gimmecode_guard:dashboard_post_id, gimmecode_guard:creation_lock

## Setup and Usage
- Install: Add app via Reddit App Directory.
- Configure: Open Mod Tools -> App Settings in your subreddit to configure options.
- Launch: Use mod menu or triggers as configured.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.52 — 2026-11-16
- Allow 0-threshold disabled, use atomic hIncrBy stats, fix Tier 1 cooldown logging, add 403 UI gate, and update README/PRIVACY

0.0.51 — 2026-11-09
- Devvit SDK v0.15.2 baseline and minor/patch dependency maintenance update.

0.0.50 — 2026-10-27
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/gimmecode-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/gimmecode-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/gimmecode-guard)
- [Support](https://www.reddit.com/r/grantdb)