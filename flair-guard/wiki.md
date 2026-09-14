# Flair Guard

Category: Moderation  
Version: v0.0.15  
Visibility: Unlisted  
Summary: Automated rule-based post flair assignment engine with delayed eligibility checks.

## Overview
Automated rule-based post flair assignment engine with delayed eligibility checks.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/flair-guard-flowchart.png)

## Key Features
- Not documented yet.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- PostSubmit: Delivered by Reddit event router to endpoint /internal/on-post-submit.
- PostCreate: Delivered by Reddit event router to endpoint /internal/on-post-create.

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- delayedProcessingEnabled: Enable Delayed Processing (boolean, default: true). When enabled, the bot waits before processing a new post to confirm it is still valid.
- delayedProcessingSeconds: Processing Delay (seconds) (number, default: DEFAULT_DELAY_SECONDS). How many seconds to wait before checking eligibility (min: 5, max: 100). Default: 20.
- skipIfRemoved: Skip if Post is Removed (boolean, default: true). Skip processing if the post is removed by the time the check runs.
- skipIfFiltered: Skip if Post is Filtered (In Modqueue) (boolean, default: true). Skip processing if the post is awaiting mod approval.
- skipIfSpam: Skip if Post is Marked as Spam (boolean, default: true). Skip processing if the post is marked as spam.
- moderatorExempt: Exempt Moderators (boolean, default: true). Exempt moderator submissions from automated flair assignment.
- triggerKeywords: Trigger Keywords (comma separated) (string, default: urgent, help, question). Comma-separated keywords to match against the submission title.
- targetPostFlairId: Target Post Flair Template ID (string, default: ). The Reddit post flair template UUID to apply when a keyword matches.

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
- Set Template ID: Paste your subreddit post flair template UUID into Target Post Flair Template ID.
- Define Keywords: Enter comma-separated trigger keywords (e.g. `urgent, help, question`).
- Save: Automated flair enforcement begins immediately on all incoming community posts.
- No complex AutoMod YAML required. Clean visual organization for your entire community.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.15 — 2026-09-14
- Standard fleet synchronization and maintenance.

0.0.14 — 2026-09-02
- Standard fleet synchronization and maintenance.

0.0.13 — 2026-08-15
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/flair-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/flair-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/flair-guard)
- [Support](https://www.reddit.com/r/grantdb)