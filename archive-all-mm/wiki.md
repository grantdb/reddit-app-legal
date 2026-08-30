# Archive All MM

Category: Modmail  
Version: v0.0.68  
Visibility: Public  
Summary: Modmail archival utility. High-volume message indexing and backup.

## Overview
Modmail archival utility. High-volume message indexing and backup.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/archive-all-mm-flowchart.png)

## Key Features
- Not documented yet.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- Archive All Modmail: Manage background Modmail archiving and review progress (Location: subreddit)

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- targetQueues: Queues to Archive (select, default: ModmailQueue.New,ModmailQueue.InProgress). Select which modmail queues should be processed by the Archive All button.

## Automation Capabilities
- Submits Automated Comments: No — Does not submit automated comments.
- Attaches Removal Notes: No — Does not attach removal notes.
- Approves Content: No — Does not approve content.
- Removes or Filters Content: No — Does not remove or filter content.
- Dispatches Modmail Alerts: No — Does not send modmail notifications.
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)

## Setup and Usage
- Install: Add Archive All Modmail to your subreddit through the Reddit App Directory.
- Configure Queues: Open Mod Tools > App Settings > Archive All Modmail and pick your target queues.
- Start Cleanup: Click Archive All Modmail (Background)** from the subreddit action menu.
- Monitor: Check Check Modmail Archive Status anytime to observe real-time progress.
- No repetitive manual clicking. Safe, automated Inbox Zero in your native workflow.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.68 — 2026-08-30
- Standard fleet synchronization and maintenance.

0.0.67 — 2026-08-27
- Fix recursive pagination deadlock and namespace locks

0.0.66 — 2026-08-15
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/archive-all-mm/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/archive-all-mm/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/archive-all-mm)
- [Support](https://www.reddit.com/r/grantdb)