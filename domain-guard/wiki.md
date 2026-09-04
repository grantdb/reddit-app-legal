# DomainGuard

Category: Security  
Version: v0.0.151  
Visibility: Public  
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
- Configure: Open GuardHub: DomainGuard Dashboard from Subreddit Mod Tools.
- Create Rules: Add your domain allowlist or blocklist in Audit Mode to safely verify matching behavior.
- Enforce: Once satisfied with audit results, switch rules to Live mode to begin automated enforcement.
- No complex regex configuration required. Full control stays in your native dashboard.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.151 — 2026-09-04
- Feature: Added automated removal reason comment cleanup (`c.delete()` / `reddit.remove()`) when filtered posts are auto-approved upon edit or manually approved from the Filtered Queue.
- Feature: Added automated post unlocking on approval if the post was previously locked.
- Feature: Added `notificationCommentId` tracking to `FilteredPostEntry` for direct targeted comment deletion.

0.0.150 — 2026-09-04
- Standard fleet synchronization and maintenance.

0.0.149 — 2026-09-02
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/domain-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/domain-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/domain-guard)
- [Support](https://www.reddit.com/r/grantdb)