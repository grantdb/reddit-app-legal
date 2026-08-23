# App Update Checker

Category: Utility  
Version: v0.0.63  
Visibility: Unlisted  
Summary: AI-powered version tracking across the fleet. Uses Gemini 2.5 to bypass external scraper blocks.

## Overview
AI-powered version tracking across the fleet. Uses Gemini 2.5 to bypass external scraper blocks.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/app-update-checker-flowchart.png)

## Key Features
- Not documented yet.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)
- http: External HTTP Fetch access [Domains: raw.githubusercontent.com, registry.npmjs.org, api.github.com]

## Triggers and Activation
### Menu Actions
- Check for App Updates: Moderator menu action (Location: subreddit)
- Mark Apps Up-to-Date: Only use after verifying installed versions in Mod Tools > Installed Apps (Location: subreddit)
- Reset App Cache: Moderator menu action (Location: subreddit)

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- extra_slugs: Extra App Slugs to Track (paragraph, default: -). Optional. Comma or newline-separated app slugs to track (e.g. suspended-remove, sticky-pro, domain-guard). Add a baseline version with slug:version (e.g. domain-guard:0.0.38).
- auto_check_enabled: Enable Daily Auto Check (boolean, default: true). If enabled, the app will automatically run an update check every day. Modmail is only sent when an update is found (or on manually-triggered checks).

## Automation Capabilities
- Submits Automated Comments: No — Does not submit automated comments.
- Attaches Removal Notes: No — Does not attach removal notes.
- Approves Content: No — Does not approve content.
- Removes or Filters Content: No — Does not remove or filter content.
- Dispatches Modmail Alerts: No — Does not send modmail notifications.
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Hashes (structured records & alias indices)

## Setup and Usage
- Install: Add App Update Checker to your subreddit through the Reddit App Directory.
- Configure Settings: Open Mod Tools > App Settings > App Update Checker to adjust notification preferences.
- Run Initial Check: Select Check for App Updates from the subreddit overflow menu to generate your first report.
- Relax: Scheduled daily audits will keep your team informed of any future releases.
- No manual app directory checking. Automated update notifications delivered directly to modmail.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.63 — 2026-08-23
- Standard fleet synchronization and maintenance.

0.0.62 — 2026-08-20
- Standard fleet synchronization and maintenance.

0.0.61 — 2026-08-20
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/app-update-checker/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/app-update-checker/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/app-update-checker)
- [Support](https://www.reddit.com/r/grantdb)