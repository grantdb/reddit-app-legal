# GimmeCode Guard

Category: Moderation  
Version: v0.0.46  
Visibility: Unlisted  
Summary: Detects low-effort give me code requests

## Overview
Detects low-effort give me code requests

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/gimmecode-guard-flowchart.png)

## Key Features
- Not documented yet.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- CommentSubmit: Delivered by Reddit event router to endpoint /internal/trigger/comment-submit.
- CommentDelete: Delivered by Reddit event router to endpoint /internal/trigger/comment-delete.

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
- Dispatches Modmail Alerts: Yes — Sends modmail notifications.
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Sorted Sets (time-series audit logs)
- Key patterns: node:http, gimmecode_guard:dashboard_post_id, gimmecode_guard:creation_lock

## Setup and Usage
- Install: Add GimmeCode Guard to your subreddit via the Reddit App Directory.
- Launch Dashboard: Open the subreddit menu (`...`) and click GimmeCode Guard Dashboard to open the interactive control center.
- Configure Thresholds: Review or adjust Tier 1 Warning, Tier 2 Report, and Tier 3 Removal point thresholds directly in the Webview.
- Test & Enforce: Test custom community expressions in the Comment Playground. Automated protection activates immediately across all new comment submissions.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.46 — 2026-09-26
- Standard fleet synchronization and maintenance.

0.0.45 — 2026-09-26
- Standard fleet synchronization and maintenance.

0.0.44 — 2026-09-24
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/gimmecode-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/gimmecode-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/gimmecode-guard)
- [Support](https://www.reddit.com/r/grantdb)