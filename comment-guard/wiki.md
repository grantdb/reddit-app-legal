# CommentGuard

Category: Moderation  
Version: v0.0.49  
Visibility: Unlisted  
Summary: Hardened code-request moderation engine with weighted scoring and Shadow DOM stability.

## Overview
Hardened code-request moderation engine with weighted scoring and Shadow DOM stability.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/comment-guard-flowchart.png)

## Key Features
- Not documented yet.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- CommentCreate: Delivered by Reddit event router to endpoint /internal/trigger/comment-guard.
- CommentSubmit: Delivered by Reddit event router to endpoint /internal/trigger/comment-guard.

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
- Sorted Sets (time-series audit logs)
- Key patterns: node:http, node:events, comment_guard:dashboard_post_id

## Setup and Usage
- Install: Add Comment Guard to your subreddit through the Reddit App Directory.
- Configure: Open GuardHub: CommentGuard Dashboard from Subreddit Mod Tools.
- Set Thresholds: Adjust the removal score sensitivity and penalty weights to match your community standards.
- Monitor: Review enforcement logs in your dashboard to refine pattern weights over time.
- No complex AutoMod rules required. Intelligent, weighted comment moderation out of the box.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.49 — 2026-08-15
- Standard fleet synchronization and maintenance.

0.0.48 — 2026-08-04
- Standard fleet synchronization and maintenance.

0.0.47 — 2026-07-27
- Optimization: Standardized GuardHub moderator caching (`guardhub:mods:{id}`) to cache full mod list array and eliminate per-event API calls.
- Safety: Added per-thread removal cap (`maxRemovalsPerThread`, default 10) to prevent over-moderation in high-volume threads.
- Feature: Added `ImportExport` webview component for settings JSON backup & restore.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/comment-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/comment-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/comment-guard)
- [Support](https://www.reddit.com/r/grantdb)