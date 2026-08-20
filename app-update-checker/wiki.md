App Update Checker
Category: Utility
Version: v0.0.62
Visibility: Unlisted
Summary: AI-powered version tracking across the fleet. Uses Gemini 2.5 to bypass external scraper blocks.

Overview
AI-powered version tracking across the fleet. Uses Gemini 2.5 to bypass external scraper blocks.

Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/app-update-checker-flowchart.png)

Key Features
- Not documented yet.

Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)
- http: External HTTP Fetch access [Domains: raw.githubusercontent.com, registry.npmjs.org, api.github.com]

Triggers and Activation
Event Triggers
- AppInstall: Subscribed in main.ts via Devvit.addTrigger({ event: 'AppInstall' }).
- AppUpgrade: Subscribed in main.ts via Devvit.addTrigger({ event: 'AppUpgrade' }).

Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

Settings Reference
- warning (paragraph, default: If): Before you continue - Before you continue

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
- Hashes (structured records & alias indices)

Setup and Usage
- Install: Add App Update Checker to your subreddit through the Reddit App Directory.
- Configure Settings: Open Mod Tools > App Settings > App Update Checker to adjust notification preferences.
- Run Initial Check: Select Check for App Updates from the subreddit overflow menu to generate your first report.
- Relax: Scheduled daily audits will keep your team informed of any future releases.
- No manual app directory checking. Automated update notifications delivered directly to modmail.*

Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.

Version History
0.0.62 — 2026-08-20
- Standard fleet synchronization and maintenance.
0.0.61 — 2026-08-20
- Standard fleet synchronization and maintenance.
0.0.60 — 2026-08-20
- Standard fleet synchronization and maintenance.

Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/app-update-checker/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/app-update-checker/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/app-update-checker)