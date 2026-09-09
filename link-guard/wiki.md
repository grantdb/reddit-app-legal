# LinkGuard

Category: Security  
Version: v0.0.17  
Visibility: Public  
Summary: Strict URL policy enforcement & link shortener filter for Reddit posts and comments.

## Overview
Strict URL policy enforcement & link shortener filter for Reddit posts and comments.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/link-guard-flowchart.png)

## Key Features
- Not documented yet.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- PostCreate: Delivered by Reddit event router to endpoint /internal/trigger/post.
- PostSubmit: Delivered by Reddit event router to endpoint /internal/trigger/post.
- CommentCreate: Delivered by Reddit event router to endpoint /internal/trigger/comment.
- CommentSubmit: Delivered by Reddit event router to endpoint /internal/trigger/comment.
- AppInstall: Delivered by Reddit event router to endpoint /internal/on-app-install.
- AppUpgrade: Delivered by Reddit event router to endpoint /internal/on-app-install.

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
- Key patterns: node:http, link_guard:dashboard_post_id, link_guard:meta

## Setup and Usage
- Install: Add Link Guard to your subreddit through the Reddit App Directory.
- Configure: Open GuardHub: LinkGuard Dashboard from Subreddit Mod Tools.
- Select Rules: Enable URL shortener filtering, threat directory matching, and custom pattern filters in Audit Mode.
- Enforce: Once satisfied with audit logs, switch your rules to Live mode.
- No dangerous manual URL clicking. Comprehensive automated link security in your native dashboard.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.17 — 2026-09-09
- Standard fleet synchronization and maintenance.

0.0.16 — 2026-09-09
- Standard fleet synchronization and maintenance.

0.0.15 — 2026-09-08
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/link-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/link-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/link-guard)
- [Support](https://www.reddit.com/r/grantdb)