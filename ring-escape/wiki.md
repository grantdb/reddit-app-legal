Ring Escape: Serpent Flagship
Category: Interactive
Version: v0.0.63
Visibility: Unlisted
Summary: Stealth infiltration game. Sabotage four systems aboard a Serpent Empire warship and escape through the rings.

Overview
Stealth infiltration game. Sabotage four systems aboard a Serpent Empire warship and escape through the rings.

Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/ring-escape-flowchart.png)

Key Features
- Stealth & Sabotage Mechanics: Deep gameplay loop requiring players to navigate a multi-level ship, stun guards tactically, and sabotage critical systems to unlock the extraction point.
- Multi-Level Progression: Escalating challenges across multiple distinct levels, ensuring players remain engaged over long play sessions.
- Persistent Global Leaderboards: Automatically tracks high scores on the main post to encourage long-term community competition and rivalry.
- Cross-Platform Support: Enjoy precise keyboard controls on desktop web browsers and highly responsive on-screen touch controls for Reddit mobile apps.
- Autonomous Game Logic: Fully automated score submission and level management. Once the event is launched, it runs entirely on its own without requiring any moderator oversight.

Permissions Used
- redis: Redis key-value storage (state tracking, caching, strike memory)

Triggers and Activation
Event Triggers
- AppInstall: Delivered by Reddit event router to endpoint /internal/on-app-install.

Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

Settings Reference
App settings are configured via Mod Tools -> App Settings.

Automation Capabilities
- Submits Automated Comments: No
- Attaches Removal Notes: No
- Approves Content: No
- Removes or Filters Content: Yes
- Dispatches Modmail Alerts: No
- Updates User or Post Flair: No

Data Storage
This app utilizes Reddit Redis storage:
- Key-Value Strings (deduplication & cooldown markers)
- Sorted Sets (time-series audit logs)
- Key Patterns: node:http

Setup and Usage
- Install: Add Ring Escape to your subreddit via the App Directory.
- App Settings: Open your subreddit's App Settings to configure optional parameters or custom messaging for the leaderboard.
- Usage: To start a community event, simply open the Mod Menu anywhere in your subreddit and select the "Create Ring Escape Post" action to spawn a new game post.

Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.

Version History
0.0.63 — 2026-08-15
- Standard fleet synchronization and maintenance.
0.0.62 — 2026-07-27
- Verification & Sync: Standardized server Hono/Devvit route handling and Redis ZSET score ranking.
0.0.61 — 2026-07-24
- Standard fleet synchronization and maintenance.

Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/ring-escape/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/ring-escape/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/ring-escape)