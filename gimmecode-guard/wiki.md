GimmeCode Guard
Category: Moderation
Version: v0.0.30
Visibility: Unlisted
Summary: Detects low-effort give me code requests

Overview
Detects low-effort give me code requests

Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/gimmecode-guard-flowchart.png)

Key Features
- Not documented yet.

Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

Triggers and Activation
Event Triggers
- CommentSubmit: Delivered by Reddit event router to endpoint /internal/on-comment-submit.

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
- Sorted Sets (time-series audit logs)

Setup and Usage
- Install: Add GimmeCode Guard to your subreddit through the Reddit App Directory.
- Configure: Open Mod Tools > App Settings > GimmeCode Guard.
- Set Thresholds: Configure your desired scores for warning replies, reports, or removals.
- Save: Automated protection activates immediately across all new comment submissions.
- No complex regex configuration required. Clean technical discussions for your developer community.*

Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.

Version History
0.0.30 — 2026-08-15
- Standard fleet synchronization and maintenance.
0.0.29 — 2026-08-05
- Standard fleet synchronization and maintenance.
0.0.29 — 2026-08-05
- Fix: Enforced smart 8,500-character body length cap on Modmail summary report generator to satisfy Reddit API's 10,000-character hard limit and prevent `Bad request` API rejections on subreddits with extensive flag histories.

Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/gimmecode-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/gimmecode-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/gimmecode-guard)