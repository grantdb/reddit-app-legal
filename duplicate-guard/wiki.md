Duplicate Guard
Category: Moderation
Version: v0.0.33
Visibility: Unlisted
Summary: Moderation app that uses onPostSubmit to detect recent duplicate subject/topic posts.

Overview
Moderation app that uses onPostSubmit to detect recent duplicate subject/topic posts.

Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/duplicate-guard-flowchart.png)

Key Features
- Not documented yet.

Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

Triggers and Activation
Event Triggers
- PostSubmit: Delivered by Reddit event router to endpoint /internal/on-post-submit.
- PostCreate: Delivered by Reddit event router to endpoint /internal/on-post-create.

Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

Settings Reference
App settings are configured via Mod Tools -> App Settings.

Automation Capabilities
- Submits Automated Comments: Yes
- Attaches Removal Notes: No
- Approves Content: No
- Removes or Filters Content: Yes
- Dispatches Modmail Alerts: No
- Updates User or Post Flair: No

Data Storage
This app utilizes Reddit Redis storage:
- Key-Value Strings (deduplication & cooldown markers)
- Sorted Sets (time-series audit logs)

Setup and Usage
- Install: Add Duplicate Guard to your subreddit through the Reddit App Directory.
- Configure: Open Mod Tools > App Settings > Duplicate Guard.
- Set Thresholds: Choose your preferred Match Mode (Strict or Balanced) and lookback post limit.
- Save: Settings apply immediately to all incoming community submissions.
- No external tools required. Automated duplicate protection right inside Reddit.*

Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.

Version History
0.0.33 — 2026-08-15
- Standard fleet synchronization and maintenance.
0.0.32 — 2026-08-01
- Standard fleet synchronization and maintenance.
0.0.31 — 2026-08-01
- Standard fleet synchronization and maintenance.

Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/duplicate-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/duplicate-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/duplicate-guard)