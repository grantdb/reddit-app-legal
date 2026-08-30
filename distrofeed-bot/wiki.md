# DistroFeed Bot

Category: Automation  
Version: v0.1.106  
Visibility: Public  
Summary: Linux aggregator. Upgraded to Gemini 2.5 metadata extraction. Fixed network permissions.

## Overview
Linux aggregator. Upgraded to Gemini 2.5 metadata extraction. Fixed network permissions.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/DistroFeed-bot-flowchart.png)

## Key Features
- % Manual & Moderator Control: Zero auto-posting or background crons. Operates via a 2-stage Mod Menu workflow.
- AI-Powered Search Grounding: Uses Google Gemini 2.5 Flash to scan DistroWatch, Phoronix, and 9to5Linux for recent major OS releases and kernel updates.
- Interactive Pre-Publish Editor: Presents candidate updates in an interactive Devvit form where moderators can customize post title, target URL, TL;DR summary, post flair, and sticky comment options.
- Deduplication Engine: Enforces Redis URL and topic slug tracking to prevent duplicate coverage.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)
- http: External HTTP Fetch access [Domains: generativelanguage.googleapis.com]

## Triggers and Activation
### Menu Actions
- DistroFeed Bot: Scout Linux distro feeds, review articles, and publish posts (Location: subreddit)
- DistroFeed Bot: Scout Linux distro feeds, review articles, and publish posts (Location: post)

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- gemini_api_key: Google Gemini API Key (string, default: -). Required. Get yours at aistudio.google.com. Used for all source scanning.
- include_major_releases: Include Major Releases (boolean, default: true). Post new distribution version releases.
- include_serious_updates: Include Serious Updates (boolean, default: true). Post significant updates: kernel releases, security patches.

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
- Sorted Sets (time-series audit logs)
- Key patterns: distrofeed:scouted_candidates, distrofeed:posted_urls

## Setup and Usage
- Install: Add DistroFeed Bot to your subreddit via the App Directory.
- App Settings: Navigate to Mod Tools > App Settings > DistroFeed Bot and provide a Google Gemini API Key (from aistudio.google.com).
- Usage: Open the subreddit Mod Menu to scout and review updates.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.1.106 — 2026-08-25
- Standard fleet synchronization and maintenance.

0.1.105 — 2026-08-15
- Standard fleet synchronization and maintenance.

0.1.104 — 2026-08-09
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/distrofeed-bot/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/distrofeed-bot/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/distrofeed-bot)
- [Support](https://www.reddit.com/r/grantdb)