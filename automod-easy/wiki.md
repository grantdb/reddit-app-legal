AutoMod Easy
Category: Moderation
Version: v0.0.135
Visibility: Public
Summary: No-code visual rule builder for AutoModerator. Generates and validates YAML configurations automatically.

Overview
No-code visual rule builder for AutoModerator. Generates and validates YAML configurations automatically.

Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/automod-easy-flowchart.png)

Key Features
- Not documented yet.

Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

Triggers and Activation
Event Triggers
- Not documented yet.

Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

Settings Reference
- Harassment Filter (string, default: -): Rule Name - Rule Name
- keywords (string, default: -): Keywords to Ban (comma separated) - Keywords to Ban (comma separated)
- reason (string, default: -): Internal Mod Note (e.g. - Internal Mod Note (e.g.

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
- Key Patterns: node:http, automod_easy:meta

Setup and Usage
- Install: Add AutoMod Easy to your subreddit through the Reddit App Directory.
- Open Trainer: Select AutoMod Easy Trainer from Subreddit Mod Tools.
- Audit Rules: Review the initial health scorecard of your current AutoMod configuration.
- Experiment: Use the Sandbox Lab to test new rules or generate patterns from spam samples.
- No scary live-testing mistakes. Safe, visual AutoModerator development inside Reddit.*

Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.

Version History
0.0.135 — 2026-08-15
- Standard fleet synchronization and maintenance.
0.0.134 — 2026-07-29
- Standard fleet synchronization and maintenance.
0.0.133 — 2026-07-29
- Standard fleet synchronization and maintenance.

Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/automod-easy/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/automod-easy/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/automod-easy)