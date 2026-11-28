> [Full User Guide](https://www.reddit.com/r/grantdb/wiki/modconnect/) | **Technical Reference & Settings Spec**

# ModConnect

Category: Moderation  
Version: v0.0.5  
Visibility: Unlisted  
Summary: ModConnect helps community moderators recruit, review, and onboard moderators directly inside Reddit.

## Overview
ModConnect helps community moderators recruit, review, and onboard moderators directly inside Reddit.

## Key Features
- Not documented yet.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- AppInstall: Delivered by Reddit event router to endpoint /internal/trigger/app-install.
- AppUpgrade: Delivered by Reddit event router to endpoint /internal/trigger/app-upgrade.

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- No custom app settings.

## Automation Capabilities
- Submits Automated Comments: No — Does not submit automated comments.
- Attaches Removal Notes: No — Does not attach removal notes.
- Approves Content: Yes — Approves content.
- Removes or Filters Content: Yes — Removes or filters non-compliant submissions.
- Dispatches Modmail Alerts: Yes — Sends modmail notifications.
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Hashes (structured records & alias indices)
- Sorted Sets (time-series audit logs)
- Key patterns: node:http, node:crypto

## Setup and Usage
- Install: Add ModConnect to your subreddit from the Reddit App Directory.
- Open Dashboard: Launch ModConnect: Moderator Dashboard from your subreddit moderation menu.
- Publish First Role: Click Create Role, choose a template, configure any eligibility rules and questions, and click Create & Open Role.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.5 — 2026-11-28
- Add Request Mod Review button when all self-completable required onboarding tasks are done to send an urgent mod-only Modmail Inbox alert with 24h cooldown and Review Requested badges; skip outbound decision modmail for demo_* applications and log ServiceError/lifecycle/mutation events

0.0.4 — 2026-11-26
- Remove redundant Devvit settings.subreddit block and AppSettingsReader fallback so the Webview Moderator Dashboard Settings tab is the single source of truth for Modmail notification templates

0.0.3 — 2026-11-24
- Initial unlisted release: Phase 1 moderator recruiting, review, pipeline, onboarding, metrics, Redis transactions, safe publication recovery, and Phase 2A automated account eligibility checks.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/modconnect/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/modconnect/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/modconnect)
- [Support](https://www.reddit.com/r/grantdb)