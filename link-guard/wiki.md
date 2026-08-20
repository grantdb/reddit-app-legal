LinkGuard
Category: Security
Version: v0.0.13
Visibility: Public
Summary: Strict URL policy enforcement & link shortener filter for Reddit posts and comments.

Overview
Strict URL policy enforcement & link shortener filter for Reddit posts and comments.

Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/link-guard-flowchart.png)

Key Features
- Not documented yet.

Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)
- http: External HTTP Fetch access [Domains: www.virustotal.com, security.cloudflare-dns.com, dns.quad9.net, urlhaus.abuse.ch, raw.githubusercontent.com]

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
- Key Patterns: node:http, link_guard:dashboard_post_id, link_guard:meta

Setup and Usage
- Install: Add Link Guard to your subreddit through the Reddit App Directory.
- Configure: Open GuardHub: LinkGuard Dashboard from Subreddit Mod Tools.
- Select Rules: Enable URL shortener resolution, threat feed matching, and custom pattern filters in Audit Mode.
- Enforce: Once satisfied with audit logs, switch your rules to Live mode.
- No dangerous manual URL clicking. Comprehensive automated link security in your native dashboard.*

Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.

Version History
0.0.13 — 2026-08-15
- Standard fleet synchronization and maintenance.
0.0.12 — 2026-07-27
- Standard fleet synchronization and maintenance.
0.0.11 — 2026-07-27
- Standard fleet synchronization and maintenance.

Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/link-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/link-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/link-guard)