# ActionGuard

Category: Moderation  
Version: v0.0.25  
Visibility: Unlisted  
Summary: Professional action moderation engine.

## Overview
Professional action moderation engine.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/action-guard-flowchart.png)

## Key Features
- Not documented yet.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- PostCreate: Delivered by Reddit event router to endpoint /internal/trigger/post.
- CommentCreate: Delivered by Reddit event router to endpoint /internal/trigger/comment.
- ModAction: Delivered by Reddit event router to endpoint /internal/trigger/modaction.

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- No custom app settings.

## Automation Capabilities
- Submits Automated Comments: No — Does not submit automated comments.
- Attaches Removal Notes: No — Does not attach removal notes.
- Approves Content: No — Does not approve content.
- Removes or Filters Content: Yes — Removes or filters non-compliant submissions.
- Dispatches Modmail Alerts: Yes — Sends modmail notifications.
- Updates User or Post Flair: Yes — Updates post or user flair based on rules.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Hashes (structured records & alias indices)
- Sorted Sets (time-series audit logs)
- Key patterns: node:http, node:events, action_guard:dashboard_post_id, action_guard:meta

## Setup and Usage
- Install: Add Action Guard to your subreddit through the Reddit App Directory.
- Configure: Open GuardHub: ActionGuard Orchestrator from Subreddit Mod Tools.
- Create Playbooks: Build your multi-action response recipes and test them in Dry-Run Mode.
- Activate: Switch verified playbooks to Live mode to begin automated orchestration.
- No external bot hosting required. Coordinated multi-action workflows directly within Reddit.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.25 — 2026-09-02
- Standard fleet synchronization and maintenance.

0.0.24 — 2026-08-15
- Standard fleet synchronization and maintenance.

0.0.23 — 2026-07-29
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/action-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/action-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/action-guard)
- [Support](https://www.reddit.com/r/grantdb)