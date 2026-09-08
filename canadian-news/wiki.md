# Canadian News

Category: News  
Version: v0.0.57  
Visibility: Public  
Summary: Regional Canadian news aggregator. Refactored to include political news as an optional subject.

## Overview
Regional Canadian news aggregator. Refactored to include political news as an optional subject.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/canadian-news-flowchart.png)

## Key Features
- % Manual Moderator Control: Zero auto-posting or background crons. You decide when news is scouted and published.
- Optimized Moderator Control Dialog: Unified moderator menu offering fresh feed scouting, instant review of cached session candidates, and cache management.
- Multi-Subject Scouting: Scout stories across Politics, Health, Science, Technology, Business, Lifestyle, or Regional news feeds.
- Pre-Publish Editor & Regional Flair Support: Review scouted candidate stories in an interactive Devvit form to customize the post title, target URL, regional post flair, and spoiler tags prior to posting.
- Spam Filtering & Deduplication: Automatically filters promotional and spam content while enforcing 30-day link deduplication in Redis.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)
- http: External HTTP Fetch access [Domains: www.cbc.ca, cbc.ca, globalnews.ca, www.theglobeandmail.com, theglobeandmail.com]

## Triggers and Activation
### Menu Actions
- Canadian News: Scout Canadian news feeds, review cached candidates, and publish posts (Location: subreddit)
- Canadian News: Scout Canadian news feeds, review cached candidates, and publish posts (Location: post)

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

## Setup and Usage
- Install: Add Canadian News App to your subreddit via the App Directory.
- Post Flair Configuration (Optional)**:
- Navigate to Subreddit Settings > Apps > Canadian News App.
- Under Post Flair IDs, enter the flair template IDs for National and provincial feeds (`flair_national`, `flair_bc`, `flair_ab`, etc.).
- When a story from a matching region is scouted, the app automatically pre-populates its flair in the editor form.
- Usage: Open the subreddit Mod Menu or post menu and click Canadian News to launch the interactive scouting workflow.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.57 — 2026-09-08
- Standard fleet synchronization and maintenance.

0.0.56 — 2026-09-02
- Standard fleet synchronization and maintenance.

0.0.56 — 2026-09-02
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/canadian-news/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/canadian-news/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/canadian-news)
- [Support](https://www.reddit.com/r/grantdb)