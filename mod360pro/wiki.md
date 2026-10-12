# Mod360 Pro

Category: Moderation  
Version: v0.0.40  
Visibility: Public  
Summary: Unified 360-degree moderation engine and waterfall pipeline consolidating 14+ moderation tools.

## Overview
Unified 360-degree moderation engine and waterfall pipeline consolidating 14+ moderation tools.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/mod360pro-flowchart.png)

## Key Features
- Sliding-Window Frequency Limiter: Configurable post-per-minute counters that clamp burst submissions and coordinated spam floods.
- Duplicate Content Fingerprinting: Per-subreddit hash caching that catches identical link and text spam across multiple accounts.
- Suspended & Shadowban Filter: Real-time user API check identifying deleted or suspended accounts before they clutter the moderation queue.
- Domain & URL Shortener Engine: Native detection for link shorteners, tracking parameters, chat links, and blacklisted domains.
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

- Basic Settings: Status & Health (keyword, default: -). Status & Health

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
- Key patterns: mod360:dashboard_post_id, mod360:rules:config, node:http, mod360:dashboard_creation_lock, mod360:qg:reports, mod360:stats:scanned

## Setup and Usage
- Install: Add Mod360 Pro to your subreddit from the Reddit App Directory.
- Open Control Center: Navigate to Mod Tools > Mod360 Pro: Control Center.
- Verify Settings in Shadow Mode: Test rules and run simulations using the in-dashboard test benches.
- Switch to Live Enforcement: Toggle operational status to Live in the Overview tab.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.40 — 2026-10-12
- Standard fleet synchronization and maintenance.

0.0.40 — 2026-10-12
- Tab Terminology Update: Renamed 'Author & Cadence' to 'Users & Rate Limits' across all navigation tabs, section headers, and documentation for clear, standard Reddit moderation terminology.
- Graceful AutoMod 404 Error Handling: Catch gRPC status 5 / 404 NOT_FOUND errors when `config/automoderator` is not configured on a subreddit, eliminating false alert banners and providing clean empty-state onboarding in the Automations Migration and Backup Vault views.

0.0.39 — 2026-10-12
- AutoModerator Backup Vault: Demoted AutoModerator to a passive safety net with up to 30 rolling Redis configuration snapshots, point-in-time rollback modal, and protected YAML editor behind safety warnings.
- AutoMod to Automations Migration Engine: Built a full converter for migrating AutoMod rules into Reddit Mod Tools Automations recipes (with 1-click token copy cards) and high-speed Mod360 Pro native rules (with dry-run preview diffs and shadow mode protection).
- Granular Rule Tri-Action Controls: Per-rule actions for AutoMod rules: Import to Mod360 Pro, Step-by-Step to Automations, Skip/Disable/Remove, plus reversible line-by-line AutoMod retirement.
- New Migrate & Integrations Domain: Added a dedicated 6th top-level domain featuring Automations Migration, Standalone App Conflict Checklist, and the AutoMod Backup Vault.
- Overview Status & Health Expansion: Upgraded the health overview with Community Health Score breakdown, Active Module Defense Matrix, Real-time Activity Pulse, and an automated Hybrid Conflict & Redundancy Scanner with one-click safe deconfliction.
- Zero Emoji Compliance: Fully aligned all new views, badges, labels, and modals with fleet-wide typography and aesthetic standards.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/mod360pro/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/mod360pro/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/mod360pro)
- [Support](https://www.reddit.com/r/grantdb)