RescueGuard
Category: Moderation
Version: v0.0.1
Visibility: Unlisted
Summary: Subreddit post-discovery & manual spotlight moderation engine for Reddit.

Overview
Subreddit post-discovery & manual spotlight moderation engine for Reddit.

Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/rescue-guard-flowchart.png)

Key Features
- Not documented yet.

Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

Triggers and Activation
Event Triggers
- Not documented yet.

Custom Post Types and Entrypoints
- None

Settings Reference
- min_age_hours (number, default: 24): Minimum Post Age (Hours) - Posts must be at least this old before being surfaced for review (default: 24h).
- candidate_limit (number, default: 5): Review Queue Batch Size - Maximum number of low-attention candidates presented in each moderator review session.
- highlight_action (select, default: flair): Spotlight Action on Approval - Action executed when a moderator approves a candidate post.
- spotlight_flair_text (string, default: 🌟 Community Spotlight): Spotlight Flair Text - Text applied to post flair when approved (e.g. " Community Spotlight").
- spotlight_comment_template (paragraph, default: 🌟 **Community Spotlight**: This post has been selected for the community showcase! Thank you u/{author} for sharing.): Spotlight Comment Template - Sticky comment text placed on approved posts. Supports {author} and {title}.

Automation Capabilities
- Submits Automated Comments: Yes
- Attaches Removal Notes: No
- Approves Content: No
- Removes or Filters Content: No
- Dispatches Modmail Alerts: No
- Updates User or Post Flair: Yes

Data Storage
This app utilizes Reddit Redis storage:
- Key-Value Strings (deduplication & cooldown markers)

Setup and Usage
- Install: Add RescueGuard to your subreddit through the Reddit App Directory.
- Configure: Open Mod Tools > App Settings > RescueGuard.
- Set Thresholds: Configure your minimum post age (e.g. 24 hours), review batch size, and spotlight flair/comment text.
- Launch Review: Open the subreddit menu and select GuardHub: RescueGuard Review.

Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.

Version History
0.0.1 — 2026-08-20
- Standard fleet synchronization and maintenance.
- All notable changes to the RescueGuard app will be documented in this file.
0.0.1 — 2026-08-20
- Initial V1 release of RescueGuard post review and spotlight discovery engine.
- day candidate scan with minimum-age filtration and low-attention engagement ranking.
- Subreddit-level moderator menu and modal review dialog with manual approve, skip, and dismiss actions.
- Configurable spotlight flair and distinguished sticky comment highlights.
- Zero-scan Redis audit logging with 60-day automatic key expiration.

Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/rescue-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/rescue-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/rescue-guard)