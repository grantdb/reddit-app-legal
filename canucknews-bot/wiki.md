# CanuckNews Bot

Category: News  
Version: v1.1.39  
Visibility: Public  
Summary: Regional Canadian news aggregation with moderator triggers.

## Overview
Regional Canadian news aggregation with moderator triggers.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/CanuckNews-bot-flowchart.png)

## Key Features
- % Manual & Moderator Control: Operates strictly on-demand. The bot will never auto-post or run background crons.
- Candidate Scouting Pipeline: Interactively scans CBC, Global News, and Globe & Mail feeds based on your selected subject focus (Health, Science, Tech, Business, Lifestyle, Regional).
- Pre-Publish Editor: Presents candidate stories in an interactive Devvit form allowing moderators to inspect and customize the post title, link URL, flair, and spoiler settings before publishing.
- Content & Spam Filtering: Automatically filters out political content and controversial topics to maintain a neutral community environment.
- Day Redis Deduplication: Prevents duplicate link submissions across all scouting runs.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)
- http: External HTTP Fetch access [Domains: www.cbc.ca, cbc.ca, globalnews.ca, www.theglobeandmail.com, theglobeandmail.com]

## Triggers and Activation
### Menu Actions
- Scout Canadian News: Moderator menu action (Location: subreddit)
- Scout Canadian News: Moderator menu action (Location: post)

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- legal_docs: Terms & Privacy (string, default: See help text for official documentation links.). legal.legal_docs_url
- flair_national: Canada / National Flair ID (string, default: -). Canada / National Flair ID
- flair_bc: British Columbia Flair ID (string, default: -). British Columbia Flair ID
- flair_ab: Alberta Flair ID (string, default: -). Alberta Flair ID
- flair_prairies: Sask/Manitoba Flair ID (string, default: -). Sask/Manitoba Flair ID
- flair_on: Ontario Flair ID (string, default: -). Ontario Flair ID
- flair_qc: Quebec Flair ID (string, default: -). Quebec Flair ID
- flair_atlantic: Atlantic Flair ID (string, default: -). Atlantic Flair ID
- flair_north: North/Territories Flair ID (string, default: -). North/Territories Flair ID

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
- Key patterns: canucknews:scouted

## Setup and Usage
- Install: Add Canuck News Bot to your subreddit via the App Directory.
- App Settings: Navigate to Mod Tools > App Settings > Canuck News Bot to map optional regional post flair IDs.
- Usage: Open the subreddit Mod Menu and click Scout Canadian News to begin scouting.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
1.1.39 — 2026-08-15
- Standard fleet synchronization and maintenance.

1.1.38 — 2026-08-09
- Standard fleet synchronization and maintenance.

1.1.37 — 2026-08-08
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/canucknews-bot/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/canucknews-bot/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/canucknews-bot)
- [Support](https://www.reddit.com/r/grantdb)