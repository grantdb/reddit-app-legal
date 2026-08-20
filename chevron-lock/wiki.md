Chevron Lock
Category: Interactive
Version: v0.0.10
Visibility: Unlisted
Summary: Stargate-inspired 7-chevron dialing console puzzle game.

Overview
Stargate-inspired 7-chevron dialing console puzzle game.

Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/chevron-lock-flowchart.png)

Key Features
- Dynamic Dialing Engine: Encode destination glyphs plus the Point of Origin (Alpha Origin) under strict time pressure across gate sequences scaling from 3 to 7 chevrons.
- Dynamic Round Types:
- Recall: Memorize a valid gate address during a brief preview window, then reconstruct it from memory.
- Repair: Detect corrupted DHD chevron slots (`?`) and substitute them with correct glyphs from the DHD pool.
- Reorder: Observe a memory preview, then swap scrambled chevron slots back into canonical sequence before time expires.
- Round Escalating Run: Smooth 3-round onboarding ramp (3 to 4 chevrons, 0 decoys) that scales up to a full 7-chevron Master Gate Lock in Round 7.
- Daily Seeded Challenge: A canonical daily address sequence shared deterministically across all players on the same UTC day.
- Server-Authoritative Engine: All scoring, sequence validation, timing checks, stability penalties, and leaderboard writes are computed strictly on the server.
- Redis Leaderboards & Tie-Handling: Subreddit all-time and daily sorted sets with score preservation (no lower-score overwrites) and high-precision timestamp tie-breaking.
- SGC Dialing Console UI: Dark graphite aesthetics, glowing teal chevrons, telemetry readouts, stability bars, and amber/red alert pulses.

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
- Removes or Filters Content: Yes
- Dispatches Modmail Alerts: No
- Updates User or Post Flair: No

Data Storage
This app utilizes Reddit Redis storage:
- Key-Value Strings (deduplication & cooldown markers)
- Hashes (structured records & alias indices)
- Sorted Sets (time-series audit logs)
- Key Patterns: node:http, chevlock:daily

Setup and Usage
- Install: Add app via Reddit App Directory.
- Open: Open Mod Tools -> App Settings in your subreddit to configure options.
- Configure: Set app options as desired.

Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.

Version History
0.0.10 — 2026-08-15
- Standard fleet synchronization and maintenance.
0.0.9 — 2026-08-01
- Standard fleet synchronization and maintenance.
0.0.8 — 2026-08-01
- Standard fleet synchronization and maintenance.

Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/chevron-lock/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/chevron-lock/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/chevron-lock)