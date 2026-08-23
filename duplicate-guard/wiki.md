# Duplicate Guard

Category: Moderation  
Version: v0.0.33  
Visibility: Unlisted  
Summary: Moderation app that uses onPostSubmit to detect recent duplicate subject/topic posts.

## Overview
Moderation app that uses onPostSubmit to detect recent duplicate subject/topic posts.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/duplicate-guard-flowchart.png)

## Key Features
- Not documented yet.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- Clear Duplicate Lock: Moderator menu action (Location: post)

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- appEnabled: Enable Duplicate Guard (boolean, default: true). Toggle the duplicate detection engine on or off.
- matchMode: Match Mode (select, default: balanced). Match Mode
- lookbackSize: Lookback Size (number, default: 50). How many recent posts to check against (5 to 100 posts, default: 50).
- ageLimitDays: Duplicate Window (Days) (number, default: 7). Only check against posts created within this many days (1 to 30 days, default: 7).
- includeSelftext: Include Selftext in Scoring (boolean, default: false). If enabled, selftext (body text) will be checked for keyword overlap on borderline title matches.
- ignoreModerators: Ignore Moderators (boolean, default: true). Do not check posts submitted by moderators.
- ignoreApprovedUsers: Ignore Approved Users (boolean, default: false). Do not check posts submitted by approved users.
- notifyAuthorOnMatch: Notify Author on Match (PM) (boolean, default: true). Send the post author a private message listing all matched duplicate posts with links.
- includeSummaryInComment: Include Match Summary in Comment (boolean, default: true). Append the breakdown list of matched duplicate posts and links to the removal/sticky comment.
- exemptFlairIds: Exempt Flair IDs/Names (Optional) (string, default: ). Comma-separated list of post flair IDs or names to exempt from duplicate checks.
- exemptTitleRegex: Exempt Post Titles (Regex) (string, default: ). Regex for post titles that should bypass duplicate checks (e.g., megathreads).
- actionOnMatch: Action on Match (select, default: filter). Action on Match
- reportReasonText: Report Reason Text (string, default: Duplicate Guard: This looks very similar to a recent post.). Report Reason Text
- commentTemplate: Comment Template (paragraph, default: This looks very similar to a recent post on the same topic and has been flagged for moderator review.). The text to leave if a comment action is selected.
- debugLogging: Enable Debug Logging (boolean, default: true). Logs scoring data to the Devvit console.

## Automation Capabilities
- Submits Automated Comments: Yes — Posts automated comments on target submissions.
- Attaches Removal Notes: No — Does not attach removal notes.
- Approves Content: No — Does not approve content.
- Removes or Filters Content: Yes — Removes or filters non-compliant submissions.
- Dispatches Modmail Alerts: No — Does not send modmail notifications.
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Sorted Sets (time-series audit logs)

## Setup and Usage
- Install: Add Duplicate Guard to your subreddit through the Reddit App Directory.
- Configure: Open Mod Tools > App Settings > Duplicate Guard.
- Set Thresholds: Choose your preferred Match Mode (Strict or Balanced) and lookback post limit.
- Save: Settings apply immediately to all incoming community submissions.
- No external tools required. Automated duplicate protection right inside Reddit.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.33 — 2026-08-15
- Standard fleet synchronization and maintenance.

0.0.32 — 2026-08-01
- Standard fleet synchronization and maintenance.

0.0.31 — 2026-08-01
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/duplicate-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/duplicate-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/duplicate-guard)
- [Support](https://www.reddit.com/r/grantdb)