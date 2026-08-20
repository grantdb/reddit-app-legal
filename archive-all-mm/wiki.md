Archive All MM
Category: Modmail
Version: v0.0.66
Visibility: Public
Summary: Modmail archival utility. High-volume message indexing and backup.

Overview
Modmail archival utility. High-volume message indexing and backup.

Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/archive-all-mm-flowchart.png)

Key Features
- Not documented yet.

Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

Triggers and Activation
Event Triggers
- Not documented yet.

Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

Settings Reference
App settings are configured via Mod Tools -> App Settings.

Automation Capabilities
- Submits Automated Comments: No
- Attaches Removal Notes: No
- Approves Content: No
- Removes or Filters Content: No
- Dispatches Modmail Alerts: No
- Updates User or Post Flair: No

Data Storage
This app utilizes Reddit Redis storage:
- Key-Value Strings (deduplication & cooldown markers)

Setup and Usage
- Install: Add Archive All Modmail to your subreddit through the Reddit App Directory.
- Configure Queues: Open Mod Tools > App Settings > Archive All Modmail and pick your target queues.
- Start Cleanup: Click Archive All Modmail (Background)** from the subreddit action menu.
- Monitor: Check Check Modmail Archive Status anytime to observe real-time progress.
- No repetitive manual clicking. Safe, automated Inbox Zero in your native workflow.*

Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.

Version History
0.0.66 — 2026-08-15
- Standard fleet synchronization and maintenance.
0.0.65 — 2026-07-29
- Standard fleet synchronization and maintenance.
0.0.64 — 2026-07-29
- Standard fleet synchronization and maintenance.

Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/archive-all-mm/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/archive-all-mm/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/archive-all-mm)