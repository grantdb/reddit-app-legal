WikiSync Bot
Category: Utility
Version: v0.0.2
Visibility: Unlisted
Summary: Subreddit wiki synchronization engine for Reddit communities.

Overview
Subreddit wiki synchronization engine for Reddit communities.

Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/wiki-sync-bot-flowchart.png)

Key Features
- Not documented yet.

Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)
- http: External HTTP Fetch access [Domains: raw.githubusercontent.com]

Triggers and Activation
Event Triggers
- AppInstall: Subscribed in main.ts via Devvit.addTrigger({ event: 'AppInstall' }).
- AppUpgrade: Subscribed in main.ts via Devvit.addTrigger({ event: 'AppUpgrade' }).

Custom Post Types and Entrypoints
- None

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
- Key Patterns: wikisync:hash:

Setup and Usage
- Install: Add WikiSync Bot to your subreddit.
- Configure: Open Mod Tools > App Settings > WikiSync Bot.
- Set Target Path: Enter the target wiki page path (e.g. `index/all-apps/wiki-sync-bot-test`).
- Test Write: Open the subreddit menu and click Update Wiki (Manual Test)** to verify the write.

Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.

Version History
0.0.2 — 2026-08-20
- Standard fleet synchronization and maintenance.
0.0.1 — 2026-08-20
- Standard fleet synchronization and maintenance.
- All notable changes to the WikiSync app will be documented in this file.
0.0.1 — 2026-08-20
- Initial V1 release for manual wiki write testing.
- Subreddit-level moderator menu action to create/update wiki pages.
- Configurable test page path and markdown content via App Settings.

Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/wiki-sync-bot/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/wiki-sync-bot/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/wiki-sync-bot)