# FlairGuard

Category: Moderation  
Version: v0.0.14  
Visibility: Unlisted  
Summary: Professional flair moderation engine.

## Overview
Professional flair moderation engine.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/flair-guard-flowchart.png)

## Key Features
- Not documented yet.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- PostSubmit: Subscribed in main.ts via Devvit.addTrigger({ event: 'PostSubmit' }).
- PostCreate: Subscribed in main.ts via Devvit.addTrigger({ event: 'PostCreate' }).

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- delayedProcessingEnabled: Enable Delayed Processing (boolean, default: true). Enable Delayed Processing
- delayedProcessingSeconds: Processing Delay (seconds) (number, default: DEFAULT_DELAY_SECONDS). Processing Delay (seconds)
- skipIfRemoved: Skip if Post is Removed (boolean, default: true). Skip if Post is Removed
- skipIfFiltered: Skip if Post is Filtered (In Modqueue) (boolean, default: true). Skip if Post is Filtered (In Modqueue)
- skipIfSpam: Skip if Post is Marked as Spam (boolean, default: true). Skip if Post is Marked as Spam
- moderatorExempt: Exempt Moderators (boolean, default: true). Exempt Moderators
- triggerKeywords: Trigger Keywords (comma separated) (string, default: urgent, help, question). Trigger Keywords (comma separated)
- targetPostFlairId: Target Post Flair Template ID (string, default: ). Target Post Flair Template ID

## Automation Capabilities
- Submits Automated Comments: No — Does not submit automated comments.
- Attaches Removal Notes: No — Does not attach removal notes.
- Approves Content: No — Does not approve content.
- Removes or Filters Content: Yes — Removes or filters non-compliant submissions.
- Dispatches Modmail Alerts: No — Does not send modmail notifications.
- Updates User or Post Flair: Yes — Updates post or user flair based on rules.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)

## Setup and Usage
- Install: Add Flair Guard to your subreddit through the Reddit App Directory.
- Configure: Open Mod Tools > App Settings > Flair Guard.
- Map Flairs: Enter your keyword triggers and corresponding flair template IDs.
- Save: Automated flair enforcement begins immediately on all incoming community posts.
- No complex AutoMod YAML required. Clean visual organization for your entire community.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.14 — 2026-09-02
- Standard fleet synchronization and maintenance.

0.0.13 — 2026-08-15
- Standard fleet synchronization and maintenance.

0.0.12 — 2026-08-04
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/flair-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/flair-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/flair-guard)
- [Support](https://www.reddit.com/r/grantdb)