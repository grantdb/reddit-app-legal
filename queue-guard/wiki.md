# QueueGuard

Category: Moderation  
Version: v0.0.42  
Visibility: Unlisted  
Summary: Queue triage and decision-support tool. Surfaces duplicate context, account signals, and prior handling history before moderators approve or remove queued posts.

## Overview
Queue triage and decision-support tool. Surfaces duplicate context, account signals, and prior handling history before moderators approve or remove queued posts.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/queue-guard-flowchart.png)

## Key Features
- Not documented yet.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- Not documented yet.

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- quickRemoveForm: Flag as Spam (boolean, default: -). Flag as Spam
- note: Internal Mod Note (Optional) (string, default: -). Internal Mod Note (Optional)

## Automation Capabilities
- Submits Automated Comments: No — Does not submit automated comments.
- Attaches Removal Notes: No — Does not attach removal notes.
- Approves Content: Yes — Approves content.
- Removes or Filters Content: Yes — Removes or filters non-compliant submissions.
- Dispatches Modmail Alerts: No — Does not send modmail notifications.
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Hashes (structured records & alias indices)
- Key patterns: node:http, gh:qg

## Setup and Usage
- Install: Add Queue-Guard to your subreddit through the Reddit App Directory.
- Configure: Risk thresholds and analyzer policies work out of the box with zero required setup.
- Use: Open the three-dots menu on any post or comment to moderate directly in your feed.
- Customize: Open [#] QueueGuard Dashboard from Subreddit Mod Tools to adjust sensitivity anytime.
- No complicated workflow changes. No separate tool required for routine moderation.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.42 — 2026-09-05
- Standard fleet synchronization and maintenance.

0.0.41 — 2026-09-02
- Standard fleet synchronization and maintenance.

0.0.40 — 2026-08-18
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/queue-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/queue-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/queue-guard)
- [Support](https://www.reddit.com/r/grantdb)