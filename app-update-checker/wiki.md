# App Update Checker

Category: Utility  
Version: v0.0.73  
Visibility: Unlisted  
Summary: Automated version tracking and release notification engine for Reddit Devvit apps. Daily silent audits and modmail alerts.

## Overview
Automated version tracking and release notification engine for Reddit Devvit apps. Daily silent audits and modmail alerts.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/app-update-checker-flowchart.png)

## Key Features
- Not documented yet.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)
- http: External HTTP Fetch access [Domains: raw.githubusercontent.com]

## Triggers and Activation
### Menu Actions
- App Update Checker: Open moderator controls for update checks, baselines, and cache (Location: subreddit)

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- auto_check_enabled: Enable Daily Auto Check (boolean, default: true). Automatically checks for app updates daily at 12:00 UTC. Modmail is only sent when a new update is found.
- include_unlisted_bots: Include Unlisted / Custom Bots in Manual Reports (boolean, default: true). Include detected moderator bots that are not in the public Reddit App Directory in manual reports as informational entries.
- extra_slugs: Extra App Slugs to Track (paragraph, default: -). Optional. Comma or newline-separated app slugs to monitor (e.g. comment-mop, bot-bouncer, sticky-pro). Add a baseline with slug:version (e.g. domain-guard:0.0.38).

## Automation Capabilities
- Submits Automated Comments: No — Does not submit automated comments.
- Attaches Removal Notes: No — Does not attach removal notes.
- Approves Content: No — Does not approve content.
- Removes or Filters Content: Yes — Removes or filters non-compliant submissions.
- Dispatches Modmail Alerts: No — Does not send modmail notifications.
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Hashes (structured records & alias indices)

## Setup and Usage
- Install: Add App Update Checker to your subreddit through the Reddit App Directory.
- Update Apps in Mod Tools: Open Mod Tools > Installed Apps in Reddit and update any outdated applications.
- Sync Baseline: Open the subreddit menu (`...`), select App Update Checker, and choose Sync All Apps as Updated to establish your confirmed tracking baseline.
- Relax: Scheduled daily audits will silently keep your team informed of any future releases.
- No manual app directory checking. Automated update notifications delivered directly to modmail.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.73 — 2026-09-01
- Standard fleet synchronization and maintenance.

0.0.71 — 2026-08-31
- Standard fleet synchronization and maintenance.

0.0.69 — 2026-08-30
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/app-update-checker/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/app-update-checker/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/app-update-checker)
- [Support](https://www.reddit.com/r/grantdb)