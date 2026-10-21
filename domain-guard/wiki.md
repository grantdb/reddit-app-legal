# DomainGuard

Category: Security  
Version: v0.0.167  
Visibility: Unlisted  
Summary: Professional URL and domain moderation engine with singleton architecture and hardened API gates.

## Overview
Professional URL and domain moderation engine with singleton architecture and hardened API gates.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/domain-guard-flowchart.png)

## Key Features
- Not documented yet.

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

- recheckFilteredPostsJob: Anywhere (live, default: -). Anywhere

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
- Install: Add Domain Guard to your subreddit through the Reddit App Directory.
- Open Dashboard: Launch GuardHub: DomainGuard Dashboard from Subreddit Mod Tools or the subreddit menu.
- Configure Rules: Add your domain allowlist or blocklist in Audit Mode to safely verify matching behavior.
- Enforce: Once satisfied with audit results, switch rules to Live mode to begin automated enforcement.
- No complex regex configuration required. Full control stays in your native dashboard.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.167 — 2026-10-21
- Standard fleet synchronization and maintenance.

0.0.167 — 2026-10-21
- Resolved Devvit admin in-line scroll trap review: rendered `InlineLaunchCard` immediately in inline feed view before loading and access-denied states, eliminating full-height scroll traps in inline post feeds.
- Enforced canonical dual-container scroller architecture in `index.css`: strictly constrained inline mode (`body:not(.app-expanded-mode) { height: 100% !important; max-height: 512px !important; overflow: hidden !important; touch-action: pan-y !important; }`) and scoped deep dashboard scrolling exclusively to Expanded Mode (`body.app-expanded-mode`).
- Enforced mobile feed budget under `@media (max-width: 480px)` (compact padding, hidden secondary text, <=360px budget).
- Implemented 8px swipe-drag threshold guard on interactive controls to prevent accidental activation during feed browsing.
- Added Redis deduplication lock in `onTrigger` to prevent concurrent `onPostCreate` and `onPostSubmit` executions, eliminating Reddit API 5-second `RESOURCE_EXHAUSTED` rate-limit errors on notification comments.
- Removed unicode emojis from `README.md` to adhere strictly to fleet Zero-Emoji policy.

0.0.166 — 2026-10-20
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/domain-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/domain-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/domain-guard)
- [Support](https://www.reddit.com/r/grantdb)