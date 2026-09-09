# RateGuard

Category: Moderation  
Version: v0.0.9  
Visibility: Public  
Summary: Dedicated submission-frequency & posting-cadence gatekeeper for Reddit.

## Overview
Dedicated submission-frequency & posting-cadence gatekeeper for Reddit.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/rate-guard-flowchart.png)

## Key Features
- Not documented yet.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- PostSubmit: Delivered by Reddit event router to endpoint /internal/trigger/post.
- PostCreate: Delivered by Reddit event router to endpoint /internal/trigger/post.
- AppInstall: Delivered by Reddit event router to endpoint /internal/on-app-install.
- AppUpgrade: Delivered by Reddit event router to endpoint /internal/on-app-install.

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
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Hashes (structured records & alias indices)
- Sorted Sets (time-series audit logs)
- Key patterns: node:http, rate_guard:dashboard_post_id, rate_guard:meta

## Setup and Usage
- Install: Add Rate Guard to your subreddit through the Reddit App Directory.
- Open Dashboard: Click GuardHub: RateGuard Dashboard from your subreddit menu.
- Set Cadence: Configure your time between posts (in days or minutes), 24-hour rolling cap, and burst limit thresholds.
- Save: The cadence engine applies immediately to all incoming community posts.
- No external servers or complicated bot hosting required. Clean, automated rate limiting inside Reddit.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.9 — 2026-09-09
- Standard fleet synchronization and maintenance.

0.0.9 — 2026-09-08
- Transformed into full Server + Webview GuardHub moderation app.
- Added interactive Webview Control Center with Cadence Policy, Template Editor with live preview, Live Redis Audit Logs, and User Cooldown Simulator.
- Added "Filter to Mod Queue" violation enforcement action alternative to post removals.
- Added customizable sticky comment removal notice template with dynamic tokens (`{next_allowed_time}`, `{time_remaining}`).
- Fixed moderator and approved user exemption verification API signatures.
- Added atomic post event deduplication (`gh:rg:proc:${postId}`) across PostSubmit and PostCreate.
- Filtered current postId from historical lookups to eliminate self-comparison false violations.
- Upgraded to Devvit SDK v0.14.3 with full Vitest test suite.

0.0.8 — 2026-09-02
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/rate-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/rate-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/rate-guard)
- [Support](https://www.reddit.com/r/grantdb)