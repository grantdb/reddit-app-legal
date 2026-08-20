FlairGuard
Category: Moderation
Version: v0.0.13
Visibility: Unlisted
Summary: Professional flair moderation engine.

Overview
Professional flair moderation engine.

Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/flair-guard-flowchart.png)

Key Features
- Not documented yet.

Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

Triggers and Activation
Event Triggers
- PostSubmit: Delivered by Reddit event router to endpoint /internal/on-post-submit.
- PostCreate: Delivered by Reddit event router to endpoint /internal/on-post-create.

Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

Settings Reference
- delayedProcessingEnabled (boolean, default: true): Processing Delay (seconds) - Processing Delay (seconds)
- skipIfRemoved (boolean, default: true): Skip if Post is Filtered (In Modqueue) - Skip if Post is Filtered (In Modqueue)
- skipIfSpam (boolean, default: true): Exempt Moderators - Exempt Moderators
- triggerKeywords (string, default: urgent): Target Post Flair Template ID - Target Post Flair Template ID

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

Setup and Usage
- Install: Add Flair Guard to your subreddit through the Reddit App Directory.
- Configure: Open Mod Tools > App Settings > Flair Guard.
- Map Flairs: Enter your keyword triggers and corresponding flair template IDs.
- Save: Automated flair enforcement begins immediately on all incoming community posts.
- No complex AutoMod YAML required. Clean visual organization for your entire community.*

Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.

Version History
0.0.13 — 2026-08-15
- Standard fleet synchronization and maintenance.
0.0.12 — 2026-08-04
- Standard fleet synchronization and maintenance.
0.0.11 — 2026-08-04
- Standard fleet synchronization and maintenance.

Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/flair-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/flair-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/flair-guard)