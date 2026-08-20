RateGuard
Category: Moderation
Version: v0.0.5
Visibility: Public
Summary: Dedicated submission-frequency & posting-cadence gatekeeper for Reddit.

Overview
Dedicated submission-frequency & posting-cadence gatekeeper for Reddit.

Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/rate-guard-flowchart.png)

Key Features
- Not documented yet.

Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

Triggers and Activation
Event Triggers
- PostSubmit: Delivered by Reddit event router to endpoint /internal/trigger/post.
- PostCreate: Delivered by Reddit event router to endpoint /internal/trigger/post.

Custom Post Types and Entrypoints
- None

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
- Hashes (structured records & alias indices)
- Sorted Sets (time-series audit logs)

Setup and Usage
- Install: Add Rate Guard to your subreddit through the Reddit App Directory.
- Configure: Open Mod Tools > App Settings > Rate Guard.
- Set Cadence: Configure your minimum time gap, 24-hour rolling cap, and burst limit thresholds.
- Save: The cadence engine applies immediately to all incoming community posts.
- No external servers or complicated bot hosting required. Clean, automated rate limiting inside Reddit.*

Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.

Version History
0.0.5 — 2026-08-20
- Standard fleet synchronization and maintenance.
0.0.4 — 2026-08-20
- Standard fleet synchronization and maintenance.
0.0.3 — 2026-08-15
- Standard fleet synchronization and maintenance.

Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/rate-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/rate-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/rate-guard)