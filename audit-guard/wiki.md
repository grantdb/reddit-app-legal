# AuditGuard

Category: Moderation  
Version: v0.0.15  
Visibility: Unlisted  
Summary: Professional audit log moderation engine.

## Overview
Professional audit log moderation engine.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/audit-guard-flowchart.png)

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

- No custom app settings.

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
- Sorted Sets (time-series audit logs)
- Key patterns: node:http, node:events, audit_guard:dashboard_post_id

## Setup and Usage
- Install: Add Audit Guard to your subreddit through the Reddit App Directory.
- Initialize Dashboard: Select GuardHub: Create Audit Dashboard from Subreddit Mod Tools.
- Record Events: Use the dashboard to log moderation actions and configuration changes.
- Review: Open your dashboard anytime to inspect event history and search specific actions.
- No external database setup required. Complete moderation transparency directly in your subreddit.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.15 — 2026-08-15
- Standard fleet synchronization and maintenance.

0.0.14 — 2026-07-29
- Standard fleet synchronization and maintenance.

0.0.13 — 2026-07-29
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/audit-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/audit-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/audit-guard)
- [Support](https://www.reddit.com/r/grantdb)