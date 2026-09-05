# UserGuard

Category: Moderation  
Version: v0.0.72  
Visibility: Public  
Summary: Native author-based moderation engine with exact username and threshold resolution.

## Overview
Native author-based moderation engine with exact username and threshold resolution.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/user-guard-flowchart.png)

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
- Approves Content: No — Does not approve content.
- Removes or Filters Content: Yes — Removes or filters non-compliant submissions.
- Dispatches Modmail Alerts: Yes — Sends modmail notifications.
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Hashes (structured records & alias indices)
- Sorted Sets (time-series audit logs)
- Key patterns: node:http, node:events, user_guard:meta

## Setup and Usage
- Install: Add User Guard to your subreddit through the Reddit App Directory.
- Configure: Open GuardHub: UserGuard Dashboard from Subreddit Mod Tools.
- Create Rules: Add your account age and karma thresholds in Audit Mode to preview matching accounts safely.
- Enforce: Switch verified rules to Live mode to begin automated gatekeeping.
- No complex YAML syntax required. Clean access controls directly in your community dashboard.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.72 — 2026-09-05
- Standard fleet synchronization and maintenance.

0.0.71 — 2026-09-02
- Standard fleet synchronization and maintenance.

0.0.70 — 2026-08-18
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/user-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/user-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/user-guard)
- [Support](https://www.reddit.com/r/grantdb)