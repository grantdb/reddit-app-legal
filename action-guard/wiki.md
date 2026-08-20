ActionGuard
Category: Moderation
Version: v0.0.24
Visibility: Unlisted
Summary: Professional action moderation engine.

Overview
Professional action moderation engine.

Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/action-guard-flowchart.png)

Key Features
- Not documented yet.

Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

Triggers and Activation
Event Triggers
- PostCreate: Delivered by Reddit event router to endpoint /internal/trigger/post.
- CommentCreate: Delivered by Reddit event router to endpoint /internal/trigger/comment.
- ModAction: Delivered by Reddit event router to endpoint /internal/trigger/modaction.

Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

Settings Reference
App settings are configured via Mod Tools -> App Settings.

Automation Capabilities
- Submits Automated Comments: No
- Attaches Removal Notes: No
- Approves Content: No
- Removes or Filters Content: Yes
- Dispatches Modmail Alerts: Yes
- Updates User or Post Flair: Yes

Data Storage
This app utilizes Reddit Redis storage:
- Key-Value Strings (deduplication & cooldown markers)
- Hashes (structured records & alias indices)
- Sorted Sets (time-series audit logs)
- Key Patterns: node:http, node:events, action_guard:dashboard_post_id, action_guard:meta

Setup and Usage
- Install: Add Action Guard to your subreddit through the Reddit App Directory.
- Configure: Open GuardHub: ActionGuard Orchestrator from Subreddit Mod Tools.
- Create Playbooks: Build your multi-action response recipes and test them in Dry-Run Mode.
- Activate: Switch verified playbooks to Live mode to begin automated orchestration.
- No external bot hosting required. Coordinated multi-action workflows directly within Reddit.*

Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.

Version History
0.0.24 — 2026-08-15
- Standard fleet synchronization and maintenance.
0.0.23 — 2026-07-29
- Standard fleet synchronization and maintenance.
0.0.22 — 2026-07-29
- Standard fleet synchronization and maintenance.

Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/action-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/action-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/action-guard)