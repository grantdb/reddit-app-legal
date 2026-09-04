# Sticky-Pro

Category: Moderation  
Version: v1.0.110  
Visibility: Public  
Summary: Automated moderator sticky suite with dynamic form population.

## Overview
Automated moderator sticky suite with dynamic form population.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/sticky-pro-flowchart.png)

## Key Features
- Unified Post Menu Popout: Open Sticky Pro from any post menu (`...`) to pick from configured templates, write custom markdown, toggle pinning and comment locks, set auto-unsticky timers, or remove active stickies.
- One-Click Unsticky Action: Select Remove Active Sticky inside the popout to immediately unpin and remove the active sticky comment and cancel any pending timers.
- Duration Expiration Timers: Automatically expire and remove sticky comments after a configurable countdown (1 hour, 6 hours, 12 hours, 24 hours, 3 days, 7 days) via scheduled background jobs.
- Auto-Sticky Posting: Can be configured to automatically submit and lock a sticky comment on every new post in the subreddit, with built-in deduplication and delayed eligibility checking.
- Auto-Pin Control: Configurable setting (`autoPin`) to control whether sticky comments are pinned to the top of the comment section or distinguished as moderator comments without pinning.
- Enhanced Comment Commands: Quick moderator commands (`!sticky 1 24h`, `!sticky 2 3d`, `!sticky 3`, `!unsticky`) available as fast mobile and desktop shortcuts.
- Reliable Deliveries: Automatically retries and bypasses platform rate limits when posting, ensuring your moderation actions never fail silently.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- Sticky Pro: Post, customize, schedule, or remove sticky comments on this submission (Location: post)

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- label1: Custom Toast Name 1 (string, default: FAQ). Sets the display name for Template 1.
- text1: Sticky Content 1 (paragraph, default: -). Sticky Content 1
- label2: Custom Toast Name 2 (string, default: Rules). Sets the display name for Template 2.
- text2: Sticky Content 2 (paragraph, default: -). Sticky Content 2
- label3: Custom Toast Name 3 (string, default: Custom). Sets the display name for Template 3.
- text3: Sticky Content 3 (paragraph, default: -). Sticky Content 3
- enableAutoSticky: Enable Auto-Sticky on Every Post (boolean, default: false). Enable Auto-Sticky on Every Post
- autoStickyText: Auto-Sticky Content (paragraph, default: -). Auto-Sticky Content
- autoPin: Pin Auto-Sticky Comment to Top (boolean, default: true). When enabled, auto-sticky comments are stickied to top of thread. When disabled, comments are distinguished as moderator without pinning.
- delayedProcessingEnabled: Enable Delayed Processing (PostCreate path) (boolean, default: true). When enabled, auto-sticky via PostCreate waits before posting to confirm the post is still live. PostSubmit always fires immediately.
- delayedProcessingSeconds: Processing Delay (seconds) (number, default: 10). How many seconds to wait on the PostCreate path before checking eligibility (min: 5, max: 100). Default: 10.
- skipIfRemoved: Skip if Post is Removed (boolean, default: true). Skip auto-sticky if the post is removed by the time the delay expires.
- skipIfFiltered: Skip if Post is Filtered (In Modqueue) (boolean, default: false). Skip auto-sticky if awaiting mod approval. Default OFF - mods often want stickies on filtered posts.
- skipIfSpam: Skip if Post is Marked as Spam (boolean, default: true). Skip auto-sticky if the post is marked as spam when the delay expires.

## Automation Capabilities
- Submits Automated Comments: Yes — Posts automated comments on target submissions.
- Attaches Removal Notes: No — Does not attach removal notes.
- Approves Content: No — Does not approve content.
- Removes or Filters Content: Yes — Removes or filters non-compliant submissions.
- Dispatches Modmail Alerts: No — Does not send modmail notifications.
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)

## Setup and Usage
- Install: Add Sticky Pro to your subreddit via the Reddit App Directory.
- App Settings:
- Navigate to your subreddit's Mod Tools > App Settings > Sticky Pro.
- Define your Markdown text and custom display labels for Template 1, 2, and 3.
- Toggle Enable Auto-Sticky on Every Post and set Pin Auto-Sticky Comment to Top (`autoPin`).
- Configure Delayed Eligibility-First processing preferences (delay duration, skip if removed, skip if spam).
- Usage:
- On any post, open the moderator menu (`...`), select Sticky Pro, and choose Post / Customize Sticky or Remove Active Sticky.
- Use `!sticky 1 24h` or `!sticky 2` in comment replies for rapid mobile shortcuts.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
1.0.110 — 2026-09-03
- Standard fleet synchronization and maintenance.

1.0.109 — 2026-09-02
- Standard fleet synchronization and maintenance.

1.0.109 — 2026-09-02
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/sticky-pro/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/sticky-pro/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/sticky-pro)
- [Support](https://www.reddit.com/r/grantdb)