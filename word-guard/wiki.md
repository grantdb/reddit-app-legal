WordGuard
Category: Moderation
Version: v0.0.185
Visibility: Public
Summary: Premium keyword moderation engine with singleton control center and hardened security architecture.

Overview
Premium keyword moderation engine with singleton control center and hardened security architecture.

Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/word-guard-flowchart.png)

Key Features
- Not documented yet.

Permissions Used
- redis: Redis key-value storage (state tracking, caching, strike memory)

Triggers and Activation
Event Triggers
- PostSubmit: Delivered by Reddit event router to endpoint /internal/trigger/post.
- PostCreate: Delivered by Reddit event router to endpoint /internal/trigger/post.
- CommentSubmit: Delivered by Reddit event router to endpoint /internal/trigger/comment.
- CommentCreate: Delivered by Reddit event router to endpoint /internal/trigger/comment.

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
- Key Patterns: node:http, word_guard:dashboard_post_id, word_guard:meta

Setup and Usage
- Install: Add Word Guard to your subreddit through the Reddit App Directory.
- Configure: Open GuardHub: WordGuard Dashboard from Subreddit Mod Tools.
- Create Groups: Add your keyword groups (e.g. Scams or Profanity) and test them in Audit Mode.
- Enforce: Switch verified groups to Live mode to begin automated keyword filtering.
- No cryptic YAML files required. Clean, modular keyword management directly in your community dashboard.*

Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.

Version History
0.0.185 — 2026-08-15
- Standard fleet synchronization and maintenance.
0.0.184 — 2026-08-10
- Standard fleet synchronization and maintenance.
0.0.183 — 2026-08-10
- Standard fleet synchronization and maintenance.

Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/word-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/word-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/word-guard)