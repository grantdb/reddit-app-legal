Reference Reply Bot
Category: Support
Version: v0.0.12
Visibility: Unlisted
Summary: Post-only support intake and reference bot for r/grantdb.

Overview
Post-only support intake and reference bot for r/grantdb.

Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/reference-reply-bot-flowchart.png)

Key Features
- Post-Only Support Focus: Listens strictly to `onPostSubmit` events to provide immediate triage and reference replies on new support submissions in `r/grantdb`.
- Confidence-Based Reply Shaping: Categorizes matched results into confidence bands (`high`, `medium`, `low`) to dynamically tailor response length, section visibility, and diagnostic blocks.
- Likely Cause & Safe-First Actions: Surfaces diagnostic `Likely cause` blocks for high/medium confidence matches and ranks safe, non-disruptive troubleshooting actions first (settings check → Mod Menu test → console logs).
- Semantic Intent Deduplication: Prunes near-duplicate troubleshooting bullets by intent signature (`dedupeBulletsByIntent`) to keep replies compact and focused.
- Atomic Concurrency Lock: Uses Redis `watch` and multi-exec transactions (`rrb:processing:`) to acquire a 30-second processing lock, preventing race conditions when event triggers fire concurrently.
- Post-Execution Replied Marker: The permanent deduplication marker (`rrb:replied:`) is written only after `submitComment` succeeds. If commenting fails, the lock is released in a `finally` block so the post can be retried safely.
- Structured Redis App Knowledge: App documentation records are stored in `rrb:apps` and `rrb:aliases` Redis hashes for easy bulk ingestion of fleet README files.

Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

Triggers and Activation
Event Triggers
- PostSubmit: Delivered by Reddit event router to endpoint /internal/on-post-submit.
- PostCreate: Delivered by Reddit event router to endpoint /internal/on-post-create.
- AppInstall: Delivered by Reddit event router to endpoint /internal/on-app-install.
- AppUpgrade: Delivered by Reddit event router to endpoint /internal/on-app-upgrade.

Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

Settings Reference
App settings are configured via Mod Tools -> App Settings.

Automation Capabilities
- Submits Automated Comments: Yes
- Attaches Removal Notes: No
- Approves Content: No
- Removes or Filters Content: Yes
- Dispatches Modmail Alerts: No
- Updates User or Post Flair: No

Data Storage
This app utilizes Reddit Redis storage:
- Key-Value Strings (deduplication & cooldown markers)
- Hashes (structured records & alias indices)
- Key Patterns: rrb:apps, rrb:aliases, rrb:meta:schemaVersion, rrb:meta:seededAt, rrb:meta:seedSource, rrb:meta:subreddit

Setup and Usage
- Install: Add app via Reddit App Directory.
- Open: Open Mod Tools -> App Settings in your subreddit to configure options.
- Configure: Set app options as desired.

Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.

Version History
0.0.12 — 2026-08-16
- Standard fleet synchronization and maintenance.
0.0.11 — 2026-08-11
- Standard fleet synchronization and maintenance.
0.0.10 — 2026-08-11
- Standard fleet synchronization and maintenance.

Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/reference-reply-bot/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/reference-reply-bot/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/reference-reply-bot)