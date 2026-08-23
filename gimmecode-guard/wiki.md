# GimmeCode Guard

Category: Moderation  
Version: v0.0.30  
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
- Check User GimmeCode History: Moderator menu action (Location: comment)
- View GimmeCode Audit Logs: Moderator menu action (Location: subreddit)

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- exemptModsAndApproved: Exempt Moderators and Approved Users (-5 points) (boolean, default: true). Exempt Moderators and Approved Users (-5 points)
- useDefaultPhrases: Use Default Phrases (e.g. "code please", "send source") (boolean, default: true). Use Default Phrases (e.g. "code please", "send source")
- customPhrases: Custom Phrases (comma-separated) (string, default: ). Custom Phrases (comma-separated)
- warnThreshold: Warning Threshold (0 to disable) (number, default: 0). Warning Threshold (0 to disable)
- reportThreshold: Report Threshold (0 to disable) (number, default: 0). Report Threshold (0 to disable)
- removeThreshold: Remove Threshold (0 to disable) (number, default: 0). Remove Threshold (0 to disable)
- warningTemplate: Warning Auto-Reply Message (string, default: Hi! It looks like you're asking for code or links. Please take a moment to leave some feedback or appreciation (e.g. 'Wow, looks great!') for the creator when making requests.). Warning Auto-Reply Message

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

## Setup and Usage
- Install: Add GimmeCode Guard to your subreddit through the Reddit App Directory.
- Configure: Open Mod Tools > App Settings > GimmeCode Guard.
- Set Thresholds: Configure your desired scores for warning replies, reports, or removals.
- Save: Automated protection activates immediately across all new comment submissions.
- No complex regex configuration required. Clean technical discussions for your developer community.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.30 — 2026-08-15
- Standard fleet synchronization and maintenance.

0.0.29 — 2026-08-05
- Standard fleet synchronization and maintenance.

0.0.29 — 2026-08-05
- Fix: Enforced smart 8,500-character body length cap on Modmail summary report generator to satisfy Reddit API's 10,000-character hard limit and prevent `Bad request` API rejections on subreddits with extensive flag histories.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/gimmecode-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/gimmecode-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/gimmecode-guard)
- [Support](https://www.reddit.com/r/grantdb)