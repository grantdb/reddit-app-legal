# VerifyGuard

Category: Security  
Version: v0.0.6  
Visibility: Public  
Summary: Configurable multi-tier verification engine for user trust, age, and role verification.

## Overview
Configurable multi-tier verification engine for user trust, age, and role verification.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/verify-guard-flowchart.png)

## Key Features
- Not documented yet.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- PostCreate: Delivered by Reddit event router to endpoint /internal/trigger/post.
- PostSubmit: Delivered by Reddit event router to endpoint /internal/trigger/post.
- CommentCreate: Delivered by Reddit event router to endpoint /internal/trigger/comment.
- CommentSubmit: Delivered by Reddit event router to endpoint /internal/trigger/comment.
- AppInstall: Delivered by Reddit event router to endpoint /internal/trigger/app-install.

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- daily-expiration-cron: Pending Queue (${queue.length}) (success, default: -). Pending Queue (${queue.length})

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
- Hashes (structured records & alias indices)
- Sorted Sets (time-series audit logs)
- Key patterns: node:http, verify_guard:dashboard_post_id

## Setup and Usage
- Install: Add Verify Guard to your subreddit through the Reddit App Directory.
- Launch Dashboard: Open the subreddit menu (`...`), select VerifyGuard, and choose Open Verification Dashboard.
- Launch Post: Open VerifyGuard and choose Create Verification Post to generate your community intake post.
- Activate: Set your desired verification tiers in the dashboard to begin welcoming verified members.
- No modmail clutter or sensitive data exposure. Streamlined community verification directly in Reddit.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.6 — 2026-09-01
- Standard fleet synchronization and maintenance.

0.0.5 — 2026-08-31
- Standard fleet synchronization and maintenance.

0.0.4 — 2026-08-15
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/verify-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/verify-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/verify-guard)
- [Support](https://www.reddit.com/r/grantdb)