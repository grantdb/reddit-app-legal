# WikiSync Bot

Category: Utility  
Version: v0.0.14  
Visibility: Unlisted  
Summary: Subreddit wiki synchronization engine for Reddit communities.

## Overview
Subreddit wiki synchronization engine for Reddit communities.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/wiki-sync-bot-flowchart.png)

## Key Features
- Not documented yet.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)
- http: External HTTP Fetch access [Domains: raw.githubusercontent.com]

## Triggers and Activation
### Menu Actions
- GuardHub: Sync Single App Wiki: Select and immediately sync the wiki page for a specific fleet app. (Location: subreddit)
- GuardHub: Sync Wiki Pages Now: Check the fleet manifest and push any newly changed wiki pages. (Location: subreddit)
- GuardHub: Force Sync All Wiki Pages: Force a complete background re-sync of all 44 app wiki pages, bypassing cache. (Location: subreddit)

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- test_page_name: Test Wiki Page Path (paragraph, default: index/all-apps/wiki-sync-bot-test). The wiki page path to create or update (e.g. index/all-apps/wiki-sync-bot-test).
- test_content: Test Wiki Content (paragraph, default: # WikiSync Bot Test Page

This is a test wiki page created by WikiSync Bot manual verification.). Markdown content to write to the specified wiki page during manual testing.

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
- Key patterns: wikisync:hash:

## Setup and Usage
- Install: Add WikiSync Bot to your subreddit.
- Configure: Open Mod Tools > App Settings > WikiSync Bot.
- Set Target Path: Enter the target wiki page path (e.g. `index/all-apps/wiki-sync-bot-test`).
- Test Write: Open the subreddit menu and click Update Wiki (Manual Test)** to verify the write.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.14 — 2026-08-23
- Standard fleet synchronization and maintenance.

0.0.13 — 2026-08-23
- Standard fleet synchronization and maintenance.

0.0.12 — 2026-08-23
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/wiki-sync-bot/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/wiki-sync-bot/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/wiki-sync-bot)
- [Support](https://www.reddit.com/r/grantdb)