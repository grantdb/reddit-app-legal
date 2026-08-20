Sticky-Pro
Category: Moderation
Version: v1.0.105
Visibility: Public
Summary: Automated moderator sticky suite with dynamic form population.

Overview
Automated moderator sticky suite with dynamic form population.

Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/sticky-pro-flowchart.png)

Key Features
- Unified Post Menu Modal: Open Sticky Pro: Post Sticky from any post menu to pick from your configured templates, write custom markdown, toggle top-pinning and comment locks, and set an optional auto-unsticky timer.
- One-Click Unsticky Action: Select Sticky Pro: Remove Sticky from the post overflow menu to immediately unpin and remove the active sticky comment and cancel any pending timers.
- Duration Expiration Timers: Automatically expire and remove sticky comments after a configurable countdown (1 hour, 6 hours, 12 hours, 24 hours, 3 days, 7 days) via scheduled background jobs.
- Auto-Sticky Posting: Can be configured to automatically submit and lock a sticky comment on every new post in the subreddit, with built-in deduplication and delayed eligibility checking.
- Auto-Pin Control: Configurable setting (`autoPin`) to control whether sticky comments are pinned to the top of the comment section or distinguished as moderator comments without pinning.
- Enhanced Comment Commands: Quick moderator commands (`!sticky 1 24h`, `!sticky 2 3d`, `!sticky 3`, `!unsticky`) available as fast mobile and desktop shortcuts.
- Reliable Deliveries: Automatically retries and bypasses platform rate limits when posting, ensuring your moderation actions never fail silently.

Permissions Used
- redis: Redis key-value storage (state tracking, caching, strike memory)

Triggers and Activation
Event Triggers
- CommentSubmit: Subscribed in main.ts via Devvit.addTrigger({ event: 'CommentSubmit' }).
- PostSubmit: Subscribed in main.ts via Devvit.addTrigger({ event: 'PostSubmit' }).
- PostCreate: Subscribed in main.ts via Devvit.addTrigger({ event: 'PostCreate' }).

Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

Settings Reference
- label1 (string, default: FAQ): Custom Toast Name 1 - Sets the display name for Template 1.
- text1 (paragraph, default: Rules): Sticky Content 1 - Sets the display name for Template 2.
- label2 (string, default: Rules): Custom Toast Name 2 - Sets the display name for Template 2.
- text2 (paragraph, default: Custom): Sticky Content 2 - Sets the display name for Template 3.
- label3 (string, default: Custom): Custom Toast Name 3 - Sets the display name for Template 3.
- text3 (paragraph, default: false): Sticky Content 3 - Sticky Content 3
- enableAutoSticky (boolean, default: false): Enable Auto-Sticky on Every Post - Enable Auto-Sticky on Every Post
- autoStickyText (paragraph, default: true): Auto-Sticky Content - Auto-Sticky Content
- autoPin (boolean, default: true): Pin Auto-Sticky Comment to Top - When enabled, auto-sticky comments are stickied to top of thread. When disabled, comments are distinguished as moderator without pinning.
- delayedProcessingEnabled (boolean, default: true): Processing Delay (seconds) - Processing Delay (seconds)
- skipIfRemoved (boolean, default: true): Skip if Post is Filtered (In Modqueue) - Skip auto-sticky if the post is removed by the time the delay expires.
- skipIfSpam (boolean, default: true): Post ID - Skip auto-sticky if the post is marked as spam when the delay expires.
- templateChoice (select, default: -): Choose Template - Choose Template
- customText (paragraph, default: -): Custom Markdown Message (Optional) - If
- pinToTop (boolean, default: true): Pin Comment to Top (Distinguish & Sticky) - Pin Comment to Top (Distinguish & Sticky)
- lockComment (boolean, default: true): Lock Comment (Prevent Replies) - Lock Comment (Prevent Replies)
- duration (select, default: -): Auto-Unsticky Timer - Automatically unpin this comment when the selected duration expires.

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

Setup and Usage
- Install: Add Sticky Pro to your subreddit via the Reddit App Directory.
- App Settings:
- Navigate to your subreddit's Mod Tools > App Settings > Sticky Pro.
- Define your Markdown text and custom display labels for Template 1, 2, and 3.
- Toggle Enable Auto-Sticky on Every Post and set Pin Auto-Sticky Comment to Top (`autoPin`).
- Configure Delayed Eligibility-First processing preferences (delay duration, skip if removed, skip if spam).
- Usage:
- On any post, open the moderator menu and select Sticky Pro: Post Sticky to launch the configuration modal.
- To remove a sticky, select Sticky Pro: Remove Sticky or comment `!unsticky`.
- Use `!sticky 1 24h` or `!sticky 2` in comment replies for rapid mobile shortcuts.

Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.

Version History
1.0.105 — 2026-08-20
- Standard fleet synchronization and maintenance.
1.0.104 — 2026-08-18
- Standard fleet synchronization and maintenance.
1.0.103 — 2026-08-18
- Standard fleet synchronization and maintenance.

Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/sticky-pro/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/sticky-pro/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/sticky-pro)