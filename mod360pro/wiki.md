# Mod360 Pro

Category: Moderation  
Version: v0.0.49  
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
- Install: Add mod360pro to your subreddit from the Reddit App Directory.
- Open Control Center: Navigate to Mod Tools > mod360pro: Control Center.
- Verify Settings in Shadow Mode: Test rules and run simulations using the in-dashboard test benches.
- Switch to Live Enforcement: Toggle operational status to Live in the Overview tab.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.49 — 2026-10-26
- Standard fleet synchronization and maintenance.

0.0.48 — 2026-10-24
- Standard fleet synchronization and maintenance.

0.0.47 — 2026-10-24
- Resilient Export Engine & Manual Download Fallback:
- Created reusable `src/webview/lib/exportFile.ts` implementing DOM-attached anchor tag clicking, 10s deferred `URL.revokeObjectURL(url)` cleanup to prevent premature blob destruction, and dual-layer clipboard write (modern `navigator.clipboard.writeText` with legacy `document.execCommand('copy')` hidden readonly `` fallback if Permissions-Policy blocks clipboard access).
- Implemented honest toast feedback (" copied to clipboard. Download was also requested, but Reddit’s iframe may block file saves.") recognizing that browsers silently suppress downloads in sandboxed iframes without `allow-downloads`.
- Added explicit 1-click `[ Copy Full Manual ]` button next to `[ Download Manual (.md) ]` in `HelpView.tsx` for immediate, zero-failure clipboard export.
- Added `[ View Raw Manual ]` escape hatch modal rendering the entire 30-article markdown in a scrollable, auto-selecting `` with 1-click `[ Copy All ]`.
- Patched Disaster Recovery JSON backup download in `App.tsx` using `exportTextFile`.
- Mobile Mode Persistence & Static Status Page Fallback:
- Implemented `isExpandedModeActive()` evaluating URL query parameters (`mode=expanded`, `entrypoint=expanded`), `sessionStorage.getItem('mod360_view_mode')`, and platform `getWebViewMode()`.
- Integrated `addWebViewModeListener` from `@devvit/client` and guarded `window.focus` handlers against accidentally reverting mobile expanded cockpit back to inline status view.
- Verified static, zero-scroll inline dashboard card (`InlineLaunchCard`) keeping complex settings and form inputs strictly in expanded mode.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/mod360pro/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/mod360pro/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/mod360pro)
- [Support](https://www.reddit.com/r/grantdb)