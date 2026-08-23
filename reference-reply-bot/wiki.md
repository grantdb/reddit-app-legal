# Reference Reply Bot

Category: Support  
Version: v0.0.14  
Visibility: Unlisted  
Summary: Post-only support intake and reference bot for r/grantdb.

## Overview
Post-only support intake and reference bot for r/grantdb.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/reference-reply-bot-flowchart.png)

## Key Features
- Post-Only Support Focus: Listens strictly to `onPostSubmit` events to provide immediate triage and reference replies on new support submissions in `r/grantdb`.
- Confidence-Based Reply Shaping: Categorizes matched results into confidence bands (`high`, `medium`, `low`) to dynamically tailor response length, section visibility, and diagnostic blocks.
- Likely Cause & Safe-First Actions: Surfaces diagnostic `Likely cause` blocks for high/medium confidence matches and ranks safe, non-disruptive troubleshooting actions first (settings check → Mod Menu test → console logs).
- Semantic Intent Deduplication: Prunes near-duplicate troubleshooting bullets by intent signature (`dedupeBulletsByIntent`) to keep replies compact and focused.
- Atomic Concurrency Lock: Uses Redis `watch` and multi-exec transactions (`rrb:processing:`) to acquire a 30-second processing lock, preventing race conditions when event triggers fire concurrently.
- Post-Execution Replied Marker: The permanent deduplication marker (`rrb:replied:`) is written only after `submitComment` succeeds. If commenting fails, the lock is released in a `finally` block so the post can be retried safely.
- Structured Redis App Knowledge: App documentation records are stored in `rrb:apps` and `rrb:aliases` Redis hashes for easy bulk ingestion of fleet README files.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- GrantDB Support: Clear My Cooldown: Reset your user testing cooldown in Redis so automated replies fire immediately. (Location: subreddit)
- GrantDB Support: Seed App Knowledge Database: Populate Redis with normalized app reference records from r/grantdb/wiki/bot_knowledge (or bundled fallback). (Location: subreddit)
- GrantDB Support: Clear Knowledge Database: Wipe stored app reference records, alias mappings, and metadata from Redis. (Location: subreddit)
- GrantDB Support: Analyze & Reply to Post: Manually run support intake analysis and post reference reply on demand. (Location: post)

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- enabled: Enable Support Bot (boolean, default: true). Master toggle to enable or pause support bot monitoring in r/grantdb.
- welcomeRepliesEnabled: Enable Support Post Welcome Replies (boolean, default: true). Automatically reply to new support posts with reference & troubleshooting guidance.
- minConfidence: Post Minimum Confidence Threshold (0-100) (number, default: 60). Minimum score required to post a welcome/reference reply on a support post.
- completenessThreshold: Intake Completeness Threshold (0.0-1.0) (number, default: 0.6). Score threshold below which matched app replies append a missing details reminder (hybrid mode).
- replyCooldownMinutes: User Cooldown Window (Minutes) (number, default: 15). Minimum time to wait before automated replies fire again for the same user. Set 0 to disable.
- supportFlairs: Monitored Support Post Flairs (string, default: Support, Bug, Bug Report, Help, Question). Comma-separated post flair names (e.g., "Support, Bug, Help, Question"). Blank = all posts.
- maxLinksPerReply: Maximum Links Per Reply (number, default: 2). Cap on documentation and reference links per reply.
- debugLogging: Enable Debug Logging (boolean, default: false). Log scoring details and lock statuses to the console.

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
- Hashes (structured records & alias indices)
- Key patterns: rrb:apps, rrb:aliases, rrb:meta:schemaVersion, rrb:meta:seededAt, rrb:meta:seedSource, rrb:meta:subreddit

## Setup and Usage
- Install: Add app via Reddit App Directory.
- Configure: Open Mod Tools -> App Settings in your subreddit to configure options.
- Launch: Use mod menu or triggers as configured.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.14 — 2026-08-23
- Standard fleet synchronization and maintenance.

0.0.13 — 2026-08-23
- Standard fleet synchronization and maintenance.

0.0.12 — 2026-08-16
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/reference-reply-bot/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/reference-reply-bot/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/reference-reply-bot)
- [Support](https://www.reddit.com/r/grantdb)