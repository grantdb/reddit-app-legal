# Mod360 Pro

Category: Moderation  
Version: v0.0.26  
Visibility: Unlisted  
Summary: Unified 360-degree moderation engine and waterfall pipeline consolidating 14+ moderation tools.

## Overview
Unified 360-degree moderation engine and waterfall pipeline consolidating 14+ moderation tools.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/mod360pro-flowchart.png)

## Key Features
- Sliding-Window Frequency Limiter: Configurable post-per-minute counters that clamp burst submissions and coordinated spam floods.
- Duplicate Content Fingerprinting: Per-subreddit hash caching that catches identical link and text spam across multiple accounts.
- Suspended & Shadowban Filter: Real-time user API check identifying deleted or suspended accounts before they clutter the moderation queue.
- Domain & URL Shortener Guard: Native detection for link shorteners, tracking parameters, chat links, and blacklisted domains.
- Multi-Group Keyword & Regex Engine: Case-insensitive matching, word boundaries, and customizable match thresholds with built-in test simulators.
- Author Verification Tiers: Restrict posting privileges based on verified email requirements, subreddit flair templates, or minimum karma milestones.
- Configurable Countdown Windows: Hold flagged items for 15m, 30m, 1h, 2h, 4h, 8h, 24h, or 48h.
- Auto-Expiration Handling: Unreviewed items in quarantine automatically expire to permanent removal once the timer concludes.
- Click Mod Release: Release and approve quarantined items directly from the mod dashboard or feed action menu.
- –100 Community Safety Score: Calculated from author age, karma ratios, email verification, and community post history.
- Native Post & Comment Menu Actions:
- `Check Reputation`: Displays comprehensive trust breakdown and violation count.
- `Quick Approve`: Approves content and clears pending quarantine timers.
- `Quick Remove`: Removes post with optional preset removal reason.
- `Export Backup to Modmail`: Dispatches full encrypted config snapshot to modmail.
- Two-Way Wiki Synchronization: Edit your rules in `r/subreddit/wiki/mod360_rules` or in the visual dashboard; changes sync bi-directionally.
- Encrypted Modmail Snapshots: Export complete configuration snapshots directly to Subreddit Modmail for permanent, tamper-proof archival.
- Zero-Risk Shadow Mode: Run new rules in passive shadow mode with audit logging before switching them to active live enforcement.

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
- Install: Add Mod360 Pro to your subreddit from the Reddit App Directory.
- Open Control Center: Navigate to Mod Tools > Mod360 Pro Dashboard.
- Verify Settings in Shadow Mode: Test rules and run simulations using the in-dashboard test benches.
- Switch to Live Enforcement: Toggle operational status to Live in the Overview tab.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.26 — 2026-09-24
- Standard fleet synchronization and maintenance.

0.0.25 — 2026-09-23
- Standard fleet synchronization and maintenance.

0.0.24 — 2026-09-23
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/mod360pro/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/mod360pro/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/mod360pro)
- [Support](https://www.reddit.com/r/grantdb)