Stargate Trivia
Category: Interactive
Version: v0.0.123
Visibility: Public
Summary: Interactive trivia engine with rich UI and global leaderboards.

Overview
Interactive trivia engine with rich UI and global leaderboards.

Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/stargate-trivia-flowchart.png)

Key Features
- Curated Content: Features a proprietary library of unique, canonical trivia questions ensuring that hardcore fans are challenged.
- Persistent Leaderboards: Encourages long-term community engagement by tracking high scores and milestones directly on the event post.
- Seamless Experience: A custom-designed, low-latency interface that ensures perfect mobile and desktop rendering without leaving the Reddit app.
- Autonomous Game Logic: Automatically handles answer validation, scoring, and session management—no moderator oversight required once the event is launched.

Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
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
- Key Patterns: node:http, node:events

Setup and Usage
- Install: Add Stargate Trivia to your subreddit via the App Directory.
- App Settings: Open your subreddit's App Settings for Stargate Trivia to configure the number of questions per round or difficulty scaling.
- Usage: To start a community event, simply open the Mod Menu anywhere in your subreddit and select the "Launch Trivia Event" action.

Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.

Version History
0.0.123 — 2026-08-15
- Standard fleet synchronization and maintenance.
0.0.122 — 2026-07-24
- Standard fleet synchronization and maintenance.
0.0.121 — 2026-07-22
- Standard fleet synchronization and maintenance.

Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/stargate-trivia/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/stargate-trivia/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/stargate-trivia)