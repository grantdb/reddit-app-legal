DomainGuard
Category: Security
Version: v0.0.147
Visibility: Public
Summary: Professional URL and domain moderation engine with singleton architecture and hardened API gates.

Overview
Professional URL and domain moderation engine with singleton architecture and hardened API gates.

Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/domain-guard-flowchart.png)

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
- Key Patterns: node:http, node:events, hover:border-slate-500

Setup and Usage
- Install: Add Domain Guard to your subreddit through the Reddit App Directory.
- Configure: Open GuardHub: DomainGuard Dashboard from Subreddit Mod Tools.
- Create Rules: Add your domain allowlist or blocklist in Audit Mode to safely verify matching behavior.
- Enforce: Once satisfied with audit results, switch rules to Live mode to begin automated enforcement.
- No complex regex configuration required. Full control stays in your native dashboard.*

Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.

Version History
0.0.147 — 2026-08-18
- Standard fleet synchronization and maintenance.
0.0.146 — 2026-08-15
- Standard fleet synchronization and maintenance.
0.0.145 — 2026-08-15
- Standard fleet synchronization and maintenance.

Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/domain-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/domain-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/domain-guard)