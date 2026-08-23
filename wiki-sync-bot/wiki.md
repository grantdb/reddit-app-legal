WikiSync Bot
Category: Utility
Version: v0.0.13
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
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

Settings Reference
- test_page_name (paragraph, default: index/all-apps/wiki-sync-bot-test): Test Wiki Page Path - The wiki page path to create or update (e.g. index/all-apps/wiki-sync-bot-test).
- test_content (paragraph, default: # WikiSync Bot Test Page

This is a test wiki page created by WikiSync Bot manual verification.): Test Wiki Content - Markdown content to write to the specified wiki page during manual testing.

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
0.0.13 — 2026-08-23
- Standard fleet synchronization and maintenance.
0.0.12 — 2026-08-23
- Standard fleet synchronization and maintenance.
0.0.11 — 2026-08-23
- Standard fleet synchronization and maintenance.

Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/wiki-sync-bot/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/wiki-sync-bot/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/wiki-sync-bot)