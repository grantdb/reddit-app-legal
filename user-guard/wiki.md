UserGuard
Category: Moderation
Version: v0.0.70
Visibility: Public
Summary: Native author-based moderation engine with exact username and threshold resolution.

Overview
Native author-based moderation engine with exact username and threshold resolution.

Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/user-guard-flowchart.png)

Key Features
- Not documented yet.

Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

Triggers and Activation
Event Triggers
- PostCreate: Delivered by Reddit event router to endpoint /internal/trigger/post.
- PostSubmit: Delivered by Reddit event router to endpoint /internal/trigger/post.
- CommentCreate: Delivered by Reddit event router to endpoint /internal/trigger/comment.
- CommentSubmit: Delivered by Reddit event router to endpoint /internal/trigger/comment.

Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

Settings Reference
App settings are configured via Mod Tools -> App Settings.

Automation Capabilities
- Submits Automated Comments: Yes
- Attaches Removal Notes: No
- Approves Content: No
- Removes or Filters Content: Yes
- Dispatches Modmail Alerts: Yes
- Updates User or Post Flair: No

Data Storage
This app utilizes Reddit Redis storage:
- Key-Value Strings (deduplication & cooldown markers)
- Hashes (structured records & alias indices)
- Sorted Sets (time-series audit logs)
- Key Patterns: node:http, node:events, user_guard:meta

Setup and Usage
- Install: Add User Guard to your subreddit through the Reddit App Directory.
- Configure: Open GuardHub: UserGuard Dashboard from Subreddit Mod Tools.
- Create Rules: Add your account age and karma thresholds in Audit Mode to preview matching accounts safely.
- Enforce: Switch verified rules to Live mode to begin automated gatekeeping.
- No complex YAML syntax required. Clean access controls directly in your community dashboard.*

Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.

Version History
0.0.70 — 2026-08-18
- Standard fleet synchronization and maintenance.
0.0.69 — 2026-08-15
- Standard fleet synchronization and maintenance.
0.0.68 — 2026-08-10
- Standard fleet synchronization and maintenance.

Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/user-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/user-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/user-guard)