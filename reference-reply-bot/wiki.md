# Reference Reply Bot

Category: Support  
Version: v0.0.33  
Visibility: Unlisted  
Summary: Post-only support intake and reference bot for r/grantdb.

## Overview
Post-only support intake and reference bot for r/grantdb.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/reference-reply-bot-flowchart.png)

## Key Features
- Not documented yet.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- GrantDB Support: Moderator Hub: Manage bot knowledge database, cooldowns, and sync status. (Location: subreddit)
- GrantDB Support: Analyze & Reply to Post: Manually run support intake analysis and post reference reply on demand. (Location: post)

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- enabled: Enable Support Bot (boolean, default: true). Master toggle to enable or pause support bot monitoring in r/grantdb.
- welcomeRepliesEnabled: Enable Support Post Welcome Replies (boolean, default: true). Automatically reply to new support posts with reference & troubleshooting guidance.
- minConfidence: Post Minimum Confidence Threshold (0-100) (number, default: 60). Minimum score required to post a welcome/reference reply on a support post.
- completenessThreshold: Intake Completeness Threshold (0.0-1.0) (number, default: 0.6). Score threshold below which matched app replies append a missing details reminder (hybrid mode).
- replyCooldownMinutes: User Cooldown Window (Minutes) (number, default: 15). Minimum time to wait before automated replies fire again for the same user. Set 0 to disable.
- supportFlairs: Monitored Support Post Flairs (string, default: Support, Bug, Bug Report, Help, Question). Comma-separated post flair names (e.g., "Support, Bug, Help, Question"). Blank = all posts.
- maxLinksPerReply: Maximum Links Per Reply (number, default: 2). Cap on documentation and reference links per reply.
- welcomeIntroTemplate: Greeting and Intro Template (string, default: Thanks for posting! While waiting for a reply, check out these helpful tips and resources for {app}:). Opening line for support replies. Use {app} for the app name.
- resolutionFooterText: Resolution Prompt Footer (string, default: *If this solved your problem, reply `fixed` to let us know!*). Footer prompt asking for confirmation. Leave blank to disable.
- fixedFlairName: Fixed Post Flair Name (string, default: Fixed). Post flair template name to apply when a user replies "fixed".
- fixedFollowUpText: Fixed Follow-Up Reply (string, default: Thanks for confirming! If possible, please reply with a brief description of what fixed the issue so it can help others.). Reply posted when a user marks a post as fixed, asking them to describe the fix.

## Automation Capabilities
- Submits Automated Comments: Yes — Posts automated comments on target submissions.
- Attaches Removal Notes: No — Does not attach removal notes.
- Approves Content: No — Does not approve content.
- Removes or Filters Content: Yes — Removes or filters non-compliant submissions.
- Dispatches Modmail Alerts: No — Does not send modmail notifications.
- Updates User or Post Flair: Yes — Updates post or user flair based on rules.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Hashes (structured records & alias indices)
- Key patterns: rrb:apps, rrb:aliases, rrb:meta:schemaVersion, rrb:meta:seededAt, rrb:meta:seedSource, rrb:meta:subreddit

## Setup and Usage
- Install: Add Reference Reply Bot to your subreddit and ensure a `Fixed` post flair template exists.
- Configure: Open Mod Tools > App Settings > Reference Reply Bot to adjust `supportFlairs`, `completenessThreshold`, `fixedFlairName`, and `fixedFollowUpText`.
- Seed Knowledge: Open the subreddit `...` menu and run GrantDB Support: Moderator Hub > Seed / Sync Knowledge Database (auto-seeds on first post if empty).

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.33 — 2026-11-13
- No pending release queued

0.0.32 — 2026-11-13
- Added CommentSubmit fixed-reply handler: updates post flair to Fixed, posts follow-up comment asking for fix details, fixed blocks.triggers manifest, and added unit tests.

0.0.31 — 2026-11-09
- Devvit SDK v0.15.2 baseline and minor/patch dependency maintenance update.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/reference-reply-bot/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/reference-reply-bot/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/reference-reply-bot)
- [Support](https://www.reddit.com/r/grantdb)