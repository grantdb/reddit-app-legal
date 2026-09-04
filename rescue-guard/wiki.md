# RescueGuard

Category: Moderation  
Version: v0.0.14  
Visibility: Unlisted  
Summary: Subreddit post-discovery & manual spotlight moderation engine for Reddit.

## Overview
Subreddit post-discovery & manual spotlight moderation engine for Reddit.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/rescue-guard-flowchart.png)

## Key Features
- Not documented yet.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- GuardHub: RescueGuard Review: Review low-attention posts from the lookback window for community spotlighting (Location: subreddit)

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- candidate_limit: Review Queue Batch Size (number, default: 5). Maximum number of candidate submissions presented in each review session (default: 5).
- min_age_hours: Minimum Post Age (Hours) (number, default: 24). Posts must be at least this old before being surfaced for review (default: 24h).
- lookback_days: Lookback Window (Days) (number, default: 30). Number of past days to scan for overlooked submissions (default: 30 days).
- enforce_single_submission: Enforce Single Submission in Lookback Window (boolean, default: true). When enabled, items or apps submitted more than once in the lookback window are excluded from spotlighting.
- dedup_strategy: Deduplication Strategy (select, default: auto). Strategy used to identify duplicate or recurring submissions across the community.
- highlight_action: Spotlight Action on Approval (select, default: none). Moderation action executed when a post is approved.
- spotlight_flair_text: Spotlight Flair Text (Optional) (string, default: ). Text of the subreddit post flair template to discover and apply. If blank or not found, flair is skipped.
- spotlight_flair_template_id: Spotlight Flair Template ID (Optional) (string, default: ). Exact post flair template ID from Subreddit Settings > Post Flair (auto-discovered from flair text if blank).
- spotlight_comment_template: Spotlight Comment Template (paragraph, default: Community Spotlight: This post has been selected for the community showcase! Thank you u/{author} for sharing.). Sticky comment text placed on approved posts. Supports {author}, {title}, and {subreddit}.

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
- Key patterns: node:http

## Setup and Usage
- Install: Add RescueGuard to your subreddit through the Reddit App Directory.
- Configure: Open Mod Tools > App Settings > RescueGuard.
- Set Thresholds: Configure your batch size, minimum post age, lookback days, deduplication strategy, and spotlight flair/comment text.
- Launch Review: Open the subreddit menu and select GuardHub: RescueGuard Review Hub.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.14 — 2026-09-04
- Standard fleet synchronization and maintenance.

0.0.13 — 2026-09-02
- Standard fleet synchronization and maintenance.

0.0.12 — 2026-08-31
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/rescue-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/rescue-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/rescue-guard)
- [Support](https://www.reddit.com/r/grantdb)