# Mod360 Pro

Category: Moderation  
Version: v0.0.12  
Visibility: Unlisted  
Summary: Unified 360-degree moderation engine and waterfall pipeline consolidating 14+ moderation tools.

## Overview
Unified 360-degree moderation engine and waterfall pipeline consolidating 14+ moderation tools.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/mod360pro-flowchart.png)

## Key Features
- Unified Frequency Limiter: Sliding-window rate limiter preventing submission floods, burst spam, and rapid-fire cross-posting.
- Domain & Shortener Guard: Built-in protection against link shorteners, affiliate redirects, and unapproved external domains.
- Regex & Keyword Engine: Multi-pattern keyword groups with word-boundary matching, case-sensitivity controls, and instant test simulation.
- Automated Shadow Parity Queue: Automatically logs discrepancies between legacy moderation actions and Mod360 Pro predictions for zero-risk migration.
- Fleet Standard Responsive Dashboard: Native, inline webview control center with smooth 48px stepped tab scrolling and mobile auto-zoom protection.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)
- http: External HTTP Fetch access [Domains: generativelanguage.googleapis.com]

## Triggers and Activation
### Menu Actions
- PostSubmit: Delivered by Reddit event router to endpoint /internal/trigger/post-submit.
- PostCreate: Delivered by Reddit event router to endpoint /internal/trigger/post-create.
- CommentSubmit: Delivered by Reddit event router to endpoint /internal/trigger/comment-submit.
- CommentCreate: Delivered by Reddit event router to endpoint /internal/trigger/comment-create.

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- No custom app settings.

## Automation Capabilities
- Submits Automated Comments: Yes — Posts automated comments on target submissions.
- Attaches Removal Notes: No — Does not attach removal notes.
- Approves Content: No — Does not approve content.
- Removes or Filters Content: Yes — Removes or filters non-compliant submissions.
- Dispatches Modmail Alerts: No — Does not send modmail notifications.
- Updates User or Post Flair: Yes — Updates post or user flair based on rules.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Key patterns: node:http, mod360:dashboard_post_id, mod360:rules:config, mod360:dashboard_creation_lock

## Setup and Usage
- Install: Add Mod360 Pro to your community via the Reddit App Directory.
- Open Dashboard: Click GuardHub: Mod360 Pro Dashboard in Subreddit Mod Tools.
- Review Shadow Mode: Review the pre-configured rules in Shadow Mode to verify accuracy against live community traffic.
- Activate Live Enforcement: Once verified, toggle the operational mode to Live Enforcement in the Overview tab.
- All settings, rules, and audit logs are managed directly within your native dashboard.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.12 — 2026-09-22
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/mod360pro/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/mod360pro/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/mod360pro)
- [Support](https://www.reddit.com/r/grantdb)