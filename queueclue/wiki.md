# QueueClue

Category: Utility  
Version: v0.0.15  
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
- SETTING_TIMEZONE: Community Time Zone (string, default: UTC). IANA time zone (e.g., America/New_York, America/Los_Angeles, Europe/London, UTC). Defaults to UTC if unset.

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
0.0.15 — 2026-11-04
- Minor update and stability fixes.

0.0.15 — 2026-11-03
- Bounded ModAction event capture: capture verified item-level removals, spam markings, and approvals via Reddit broker triggers.
- Optimistic locking and bounded Redis storage: subreddit-scoped 7-day retention capped at 5 records per item with conflict retry loops.
- Exact approval chronology: distinguishes verified subsequent approvals from unsequenced approvals, preserving intervening action history.
- Unsuppressed bounded moderation-log lookup: queries mod-log on every inspection so newer manual actions are never hidden by cached records.

0.0.14 — 2026-11-02
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/queueclue/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/queueclue/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/queueclue)
- [Support](https://www.reddit.com/r/grantdb)