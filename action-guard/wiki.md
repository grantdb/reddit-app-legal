# ActionGuard

Category: Moderation  
Version: v0.0.30  
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

- test_user: Dashboard (success, default: -). Dashboard

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
- Key patterns: node:http, node:events, action_guard:dashboard_post_id, action_guard:creation_lock

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
0.0.30 — 2026-09-20
- Standard fleet synchronization and maintenance.

0.0.29 — 2026-09-18
- Standard fleet synchronization and maintenance.

0.0.29 — 2026-09-17
- Feat: Applied fleet scrolling standard with canonical two-tier top bar header scrolling (◀ and ▶), 48px fine-tuned steps, continuous long-press, visible scrollbars, and active-tab auto-alignment.
- UI: Added mobile floating scroll controls (▲ and ▼ 48px FABs) via `ScrollSidebar`.
- UI: Added gutter-docked modal scroll controls in `RuleEditor` with `body.modal-open` viewport scroll locking.
- Fix: Replaced nested scroll trap with `overscroll-y-auto` and full desktop/mobile high-contrast scrollbars.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/action-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/action-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/action-guard)
- [Support](https://www.reddit.com/r/grantdb)