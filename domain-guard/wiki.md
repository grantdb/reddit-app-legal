> [Full User Guide](https://www.reddit.com/r/grantdb/wiki/domain-guard/) | **Technical Reference & Settings Spec**

# DomainGuard

Category: Security  
Version: v0.0.175  
Visibility: Unlisted  
Summary: Professional URL and domain moderation engine with singleton architecture and hardened API gates.

## Overview
Professional URL and domain moderation engine with singleton architecture and hardened API gates.

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

- droidappshowcase: 15m (devvit-internal, default: -). 15m

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
- Key patterns: t3_post1:edit:1, t1_comment1:create:1, t3_dm_blocked:create:1, t3_quiet_remove:create:1, t3_temp_post:create:1, t3_dryrun_rule:create:1

## Setup and Usage
- Install: Add DomainGuard to your subreddit via the Reddit Developer portal.
- Open Dashboard: From your subreddit menu (`...`), select GuardHub: DomainGuard Dashboard and add your allowlist/blocklist rules.
- Verify & Enforce: Test rules in the built-in Test Console or Dry Run mode, then switch to Enforce mode.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.175 — 2026-11-26
- Add Silent Temp Remove (temp_remove) action with restricted-link ModNote and edit-recheck tracking, route cleaned posts to Needs Review queue as 'Restricted link removed - needs review' when auto-approve is off, add fine-grained lifecycle settings (cleanRecheckAction, cleanReviewModNote, addModNoteOnAction, cleanupNotificationOnClean, unlockOnClean, autoRemoveOnExpire, alwaysAllowedDomains), enforce rule.enabled and per-rule dryRun, and guard dashboard self-heal

0.0.174 — 2026-11-22
- Add configurable minutes/hours Time Between Checks with Devvit Web scheduler task registration, ignore self-triggered filter spamlink modactions, add subreddit modmail fallback for DM-restricted users, and omit SPAM_WARNING label on non-spam removals

0.0.173 — 2026-11-18
- Guarantee approved and auto-approved posts are never marked as spam, fix comment triggers evaluating parent post, remove duplicate post menu launcher, and retry transient gRPC 500 on mod check

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/domain-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/domain-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/domain-guard)
- [Support](https://www.reddit.com/r/grantdb)