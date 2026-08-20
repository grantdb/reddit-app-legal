Guard Hub
Category: Moderation
Version: v0.0.12
Visibility: Unlisted
Summary: Central GuardHub integration platform.

Overview
Central GuardHub integration platform.

Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/guard-hub-flowchart.png)

Key Features
- Not documented yet.

Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)

Triggers and Activation
Event Triggers
- Not documented yet.

Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

Settings Reference
- placeholder (string, default: Reserved): GuardHub: Status - GuardHub: Status

Automation Capabilities
- Submits Automated Comments: No
- Attaches Removal Notes: No
- Approves Content: No
- Removes or Filters Content: No
- Dispatches Modmail Alerts: No
- Updates User or Post Flair: No

Data Storage
This app does not store state in Redis.

Setup and Usage
- Install: Add Guard Hub to your subreddit through the Reddit App Directory.
- Open Hub: Launch GuardHub: Guard Hub Dashboard from Subreddit Mod Tools.
- Review: Guard Hub automatically discovers your installed apps and displays your community defense status.
- Monitor: Check the dashboard periodically to ensure all moderation layers remain fully operational.
- No complex configuration required. Complete observability for your entire moderation ecosystem.*

Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.

Version History
0.0.12 — 2026-08-15
- Standard fleet synchronization and maintenance.
0.0.11 — 2026-07-27
- Standard fleet synchronization and maintenance.
0.0.61 — 2026-07-27
- Configuration: Added `Devvit.configure({ redditAPI: true, redis: true })`.
- UX: Restricted Status menu item to moderators (`forUserType: 'moderator'`).

Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/guard-hub/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/guard-hub/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/guard-hub)