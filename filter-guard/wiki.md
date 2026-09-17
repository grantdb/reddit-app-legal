# FilterGuard

Category: Moderation  
Version: v0.0.81  
Visibility: Unlisted  
Summary: Grouped threshold-based and gate-style filtering engine for complex community safety gates.

## Overview
Grouped threshold-based and gate-style filtering engine for complex community safety gates.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/filter-guard-flowchart.png)

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
- Submits Automated Comments: Yes — Posts automated comments on target submissions.
- Attaches Removal Notes: No — Does not attach removal notes.
- Approves Content: Yes — Approves content.
- Removes or Filters Content: Yes — Removes or filters non-compliant submissions.
- Dispatches Modmail Alerts: Yes — Sends modmail notifications.
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Hashes (structured records & alias indices)
- Sorted Sets (time-series audit logs)
- Key patterns: node:http, node:events, filter_guard:dashboard_post_id, filter_guard:meta

## Setup and Usage
- Install: Add Filter Guard to your subreddit through the Reddit App Directory.
- Open Dashboard: Access the GuardHub: FilterGuard Dashboard from your Subreddit Mod Tools.
- Configure Gates: Define your threshold groups and test them against candidate users in the Test tab.
- Enforce: Activate your verified rule groups to start automated community gating.
- No complex YAML syntax required. Clean layered protection managed directly from your native dashboard.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.81 — 2026-09-15
- Standard fleet synchronization and maintenance.

0.0.80 — 2026-09-15
- Standard fleet synchronization and maintenance.

0.0.79 — 2026-09-14
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/filter-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/filter-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/filter-guard)
- [Support](https://www.reddit.com/r/grantdb)