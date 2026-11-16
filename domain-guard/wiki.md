> [Full User Guide](https://www.reddit.com/r/grantdb/wiki/domain-guard/) | **Technical Reference & Settings Spec**

# DomainGuard

Category: Security  
Version: v0.0.171  
Visibility: Unlisted  
Summary: Professional URL and domain moderation engine with singleton architecture and hardened API gates.

## Overview
Professional URL and domain moderation engine with singleton architecture and hardened API gates.

## Key Features
- High-Precision Moderation Rules: Dynamic pattern matching and content enforcement.
- Idempotency: Powered by `devvit-utils` TaskRunner to guarantee exact-once execution and zero-drift state sync.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- PostCreate: Delivered by Reddit event router to endpoint /internal/trigger/post.
- PostSubmit: Delivered by Reddit event router to endpoint /internal/trigger/post.
- PostUpdate: Delivered by Reddit event router to endpoint /internal/trigger/post-update.
- CommentCreate: Delivered by Reddit event router to endpoint /internal/trigger/comment.
- CommentSubmit: Delivered by Reddit event router to endpoint /internal/trigger/comment.
- ModAction: Delivered by Reddit event router to endpoint /internal/trigger/modaction.
- AppInstall: Delivered by Reddit event router to endpoint /internal/on-app-install.
- AppUpgrade: Delivered by Reddit event router to endpoint /internal/on-app-install.

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- recheckFilteredPostsJob: Dashboard (devvit-internal, default: -). Dashboard

## Automation Capabilities
- Submits Automated Comments: Yes — Posts automated comments on target submissions.
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
- Key patterns: node:http, node:events, hover:border-slate-500

## Setup and Usage
- Install: Add app via Reddit App Directory.
- Configure: Open Mod Tools -> App Settings in your subreddit to configure options.
- Launch: Use mod menu or triggers as configured.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.171 — 2026-11-16
- Migrate to archivable Modmail, track removelink, fix getModNotes subredditName, validate settings/delete-rule, align TestConsole, and update README

0.0.170 — 2026-11-09
- Devvit SDK v0.15.2 baseline and minor/patch dependency maintenance update.

0.0.169 — 2026-10-27
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/domain-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/domain-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/domain-guard)
- [Support](https://www.reddit.com/r/grantdb)