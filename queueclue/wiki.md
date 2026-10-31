# QueueClue

Category: Utility  
Version: v0.0.10  
Visibility: Unlisted  
Summary: Find the available source and reason behind a queue item.

## Overview
Find the available source and reason behind a queue item.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/queueclue-flowchart.png)

## Key Features
- Not documented yet.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)

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
This app does not store persistent state in Redis.

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
0.0.10 — 2026-10-31
- Standard fleet synchronization and maintenance.

0.0.9 — 2026-10-31
- Standard fleet synchronization and maintenance.

0.0.8 — 2026-10-31
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/queueclue/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/queueclue/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/queueclue)
- [Support](https://www.reddit.com/r/grantdb)