# QueueClue

Category: Utility  
Version: v0.0.19  
Visibility: Public  
Summary: Find the available source and reason behind a queue item.

## Overview
Find the available source and reason behind a queue item.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/queueclue-flowchart.png)

## Key Features
- Not documented yet.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- QueueClue: Why filtered?: Find the available source and reason behind a queue item (Location: post)
- QueueClue: Why filtered?: Find the available source and reason behind a queue item (Location: comment)

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- SETTING_ENABLE_POSTS: Enable for posts (boolean, default: true). Allow moderators to open QueueClue on posts.
- SETTING_ENABLE_COMMENTS: Enable for comments (boolean, default: true). Allow moderators to open QueueClue on comments.
- SETTING_SHOW_AUTHOR_CONTEXT: Show author signals for unstated rules (boolean, default: true). Display author account age and karma when AutoModerator filters without providing an explicit action reason.
- SETTING_TIMEZONE: Community Time Zone (select, default: UTC). Select your community’s primary time zone to display local dates and times alongside UTC.
- SETTING_CUSTOM_TIMEZONE: Custom IANA Time Zone Identifier (string, default: ). Only used if Community Time Zone is set to "Custom". Enter any valid IANA identifier (e.g. America/Sao_Paulo).

## Automation Capabilities
- Submits Automated Comments: No — Does not submit automated comments.
- Attaches Removal Notes: No — Does not attach removal notes.
- Approves Content: No — Does not approve content.
- Removes or Filters Content: Yes — Removes or filters non-compliant submissions.
- Dispatches Modmail Alerts: No — Does not send modmail notifications.
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)

## Setup and Usage
- Install: Add QueueClue to your subreddit through the Reddit App Directory.
- Open Queue: Navigate to your subreddit's Needs Review queue in desktop Reddit Mod Tools.
- Inspect Item: Click the moderator menu (shield icon on queue cards, or overflow menu `...`) on any queued post or comment and select QueueClue: Why filtered?**.
- Review Explanation: View the available filtering source and reason in the popover modal without modifying item state.
- Zero configuration required. Post and comment explanations are enabled out-of-the-box with sensible defaults.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.19 — 2026-11-11
- Unified timeline evidence presentation: unhides mod log details, removal reasons, and mod notes when ModAction removal history is present instead of returning early on actor/timestamp.
- Stickied & distinguished removal comment detection: extracts public removal notices left by moderators or AutoModerator directly quoting rules or instructions.
- Plain-English platform removal categories: translates raw `removedByCategory` values (`automod_filtered`, `reddit`, `anti_evil_ops`, `copyright_takedown`, etc.) into actionable descriptions with administrative context.
- Author community records summary: parses author mod notes to surface prior community history (removals, warnings, bans, spam flags) at a glance.
- Extended author signals: surfaces community-specific karma breakdown, email verification state, and approved contributor / ban flags alongside global age and karma.
- Structured non-PII operational diagnostics: emits `event=inspection_diagnostics` recording branch, evidence sources consulted, and new information yield without logging usernames.
- Capture AutoModerator filter event author in persistent storage.

0.0.18 — 2026-11-09
- Devvit SDK v0.15.2 baseline and minor/patch dependency maintenance update.

0.0.17 — 2026-11-07
- Subreddit Time & Relative Elapsed Time: replaced plain UTC timestamps with human-readable relative elapsed time (e.g. `12 minutes ago`) paired with local Subreddit Time and UTC reference.
- Community Time Zone Dropdown: upgraded settings to a curated selector covering major regional community time zones with custom IANA fallback.
- Unmoderated queue clean submission detection: identifies incoming posts in the unmoderated queue awaiting initial review with zero flags, reports, or removals.
- Reddit native removal reason display: presents recorded moderator removal reasons, rule titles, and notes (`modReasonTitle`, `removalReason`, `modReasonBy`).
- Reddit automated safety filter detection: identifies posts filtered by Reddit's automated safety systems (managed under Mod Tools > Safety Filters / Reputation Filter, and spam filters).
- Author account signals for unstated AutoMod rules: safely fetches account age at post time and karma on-demand to explain AutoMod rules with "No reason supplied", backed by configurable settings toggle (`showAuthorContext`).
- Comment crowd control & collapsed reasons: surfaces exact `collapsedReason` and crowd control flags on comments.
- Link post domain and grouped reports: highlights submitted domains and groups community reports.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/queueclue/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/queueclue/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/queueclue)
- [Support](https://www.reddit.com/r/grantdb)