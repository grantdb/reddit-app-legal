# Mod360 Pro

Category: Moderation  
Version: v0.0.25  
Visibility: Unlisted  
Summary: Unified 360-degree moderation engine and waterfall pipeline consolidating 14+ moderation tools.

## Overview
Unified 360-degree moderation engine and waterfall pipeline consolidating 14+ moderation tools.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/mod360pro-flowchart.png)

## Key Features
- Suspended Account Pre-Filter: Sub-10ms fast gate rejecting suspended, shadowbanned, or deleted accounts before other checks run.
- Timed Quarantine State Machine: Configure blocked domains and suspended accounts to filter into temporary quarantine for a set duration (15m, 30m, 1h, 2h, 4h, 8h, 24h, 48h) before permanent removal.
- Verification Tiers & Email Gates: Require approved author flair templates, flair badges, or verified Reddit email addresses.
- Topic Guide Suggestions: Automatically match submissions against community guide topics and post helpful guide links on clean posts.
- Reputation Safety Score & Mod Menu Actions: 0–100 reputation score calculated from account age, karma, and status with in-feed menu actions (`Check Reputation`, `Quick Approve`, `Quick Remove`).
- False-Positive Rescue Hub: Triage hub in dashboard capturing edge-case removals for instant 1-click restoration.
- Two-Way Wiki Policy Sync: Synchronize active content rules, domain policies, and user gates directly to and from `r/subreddit/wiki/mod360_rules`.
- Disaster Recovery Backup: 1-click snapshot dispatching the entire encrypted configuration to mod team modmail for permanent backup.
- Sliding-Window Frequency Limiter: Redis sliding-window counters preventing burst spam, rapid submissions, and cross-posting floods.
- Domain & Shortener Guard: Built-in blocklists for URL shorteners, chat invites, tracking parameters, and unapproved domains.
- Regex & Keyword Engine: Multi-pattern keyword groups with word-boundary matching, case-sensitivity controls, and instant test simulation.
- High-Contrast Responsive Dashboard: Native webview control center with theme switching, fullscreen mode, 48px stepped tab navigation, zero raw emojis, and mobile auto-zoom protection.

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
- Approves Content: Yes — Approves content.
- Removes or Filters Content: Yes — Removes or filters non-compliant submissions.
- Dispatches Modmail Alerts: Yes — Sends modmail notifications.
- Updates User or Post Flair: Yes — Updates post or user flair based on rules.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Key patterns: node:http, mod360:dashboard_post_id, mod360:rules:config, mod360:dashboard_creation_lock

## Setup and Usage
- Install: Add Mod360 Pro to your community via the Reddit App Directory.
- Open Dashboard: Click Mod360 Pro Dashboard in Subreddit Mod Tools.
- Review Shadow Mode: Review the pre-configured rules in Shadow Mode to verify accuracy against live community traffic.
- Activate Live Enforcement: Once verified, toggle the operational mode to Live Enforcement in the Overview tab.
- All settings, rules, wiki sync, and audit logs are managed directly within your native dashboard.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.25 — 2026-09-23
- Standard fleet synchronization and maintenance.

0.0.24 — 2026-09-23
- Standard fleet synchronization and maintenance.

0.0.23 — 2026-09-23
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/mod360pro/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/mod360pro/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/mod360pro)
- [Support](https://www.reddit.com/r/grantdb)