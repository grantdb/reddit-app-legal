# FormatGuard

Category: Moderation  
Version: v0.0.63  
Visibility: Unlisted  
Summary: Focused structure-first moderation engine for formatting, title-shape, and stylistic rules.

## Overview
Focused structure-first moderation engine for formatting, title-shape, and stylistic rules.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/format-guard-flowchart.png)

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
- Dispatches Modmail Alerts: Yes — Sends modmail notifications.
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Hashes (structured records & alias indices)
- Sorted Sets (time-series audit logs)
- Key patterns: node:http, node:events, format_guard:dashboard_post_id, format_guard:meta

## Setup and Usage
- Install: Add Format Guard to your subreddit through the Reddit App Directory.
- Configure: Open GuardHub: FormatGuard Dashboard from Subreddit Mod Tools.
- Create Rules: Add your required title tags and length limits, testing them in the Test tab.
- Enforce: Activate your rules to begin automated formatting validation.
- No complex AutoMod syntax required. Clean, consistent post formatting across your entire community.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.63 — 2026-08-15
- Standard fleet synchronization and maintenance.

0.0.62 — 2026-07-27
- Optimization: Standardized GuardHub moderator caching (`guardhub:mods:{id}`) with 15-minute Redis expiration.
- Resilience: Added live item eligibility pre-check (`getPostById` / `getCommentById`).
- Server: Streamlined permission checks and normalized error responses `{ error, status }`.
- Webview UX: Added keyboard shortcuts (`Escape` modal close), floating toast notifications, and deferred data fetching (`requestIdleCallback`).

0.0.61 — 2026-07-24
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/format-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/format-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/format-guard)
- [Support](https://www.reddit.com/r/grantdb)