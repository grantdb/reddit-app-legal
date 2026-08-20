VerifyGuard
Category: Security
Version: v0.0.4
Visibility: Public
Summary: Configurable multi-tier verification engine for user trust, age, and role verification.

Overview
Configurable multi-tier verification engine for user trust, age, and role verification.

Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/verify-guard-flowchart.png)

Key Features
- Not documented yet.

Permissions Used
- redis: Redis key-value storage (state tracking, caching, strike memory)

Triggers and Activation
Event Triggers
- PostCreate: Delivered by Reddit event router to endpoint /internal/trigger/post.
- PostSubmit: Delivered by Reddit event router to endpoint /internal/trigger/post.
- CommentCreate: Delivered by Reddit event router to endpoint /internal/trigger/comment.
- CommentSubmit: Delivered by Reddit event router to endpoint /internal/trigger/comment.
- AppInstall: Delivered by Reddit event router to endpoint /internal/trigger/app-install.

Custom Post Types and Entrypoints
- None

Settings Reference
- daily-expiration-cron (success, default: -): Pending Queue (${queue.length}) - Pending Queue (${queue.length})

Automation Capabilities
- Submits Automated Comments: No
- Attaches Removal Notes: No
- Approves Content: No
- Removes or Filters Content: Yes
- Dispatches Modmail Alerts: No
- Updates User or Post Flair: Yes

Data Storage
This app utilizes Reddit Redis storage:
- Key-Value Strings (deduplication & cooldown markers)
- Hashes (structured records & alias indices)
- Sorted Sets (time-series audit logs)

Setup and Usage
- Install: Add Verify Guard to your subreddit through the Reddit App Directory.
- Configure: Open GuardHub: VerifyGuard Dashboard from Subreddit Mod Tools.
- Launch Post: Click GuardHub: Create Verification Post to create your community intake post.
- Activate: Set your desired verification tiers to begin welcoming verified members.
- No modmail clutter or sensitive data exposure. Streamlined community verification directly in Reddit.*

Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.

Version History
0.0.4 — 2026-08-15
- Standard fleet synchronization and maintenance.
0.0.3 — 2026-08-10
- Standard fleet synchronization and maintenance.
0.0.2 — 2026-08-10
- Standard fleet synchronization and maintenance.

Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/verify-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/verify-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/verify-guard)