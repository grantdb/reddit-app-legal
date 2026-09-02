# Canadian News

Category: News  
Version: v0.0.56  
Visibility: Public  
Summary: Regional Canadian news aggregator. Refactored to include political news as an optional subject.

## Overview
Regional Canadian news aggregator. Refactored to include political news as an optional subject.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/canadian-news-flowchart.png)

## Key Features
- % Manual Moderator Control: Zero auto-posting or background crons. You decide when news is scouted and published.
- Multi-Subject Scouting: Scout stories across Politics, Health, Science, Technology, Crime, Business, Lifestyle, or Regional news feeds.
- Pre-Publish Editor: Review scouted candidate stories in an interactive Devvit form to customize the post title, target URL, and spoiler tags prior to posting.
- Spam Filtering & Deduplication: Automatically filters promotional and spam content while enforcing 30-day link deduplication in Redis.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)
- http: External HTTP Fetch access [Domains: www.cbc.ca, cbc.ca, globalnews.ca, www.theglobeandmail.com, theglobeandmail.com]

## Triggers and Activation
### Menu Actions
- Canadian News: Scout News: Scout Canadian news feeds and draft posts (Location: subreddit)
- Canadian News: Scout News: Scout Canadian news feeds and draft posts (Location: post)

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- legal_docs: Terms & Privacy (string, default: See help text for official documentation links.). legal.legal_docs_url

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
- Usage: Open the subreddit Mod Menu and click Scout Canadian News to launch the interactive scouting workflow.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.56 — 2026-09-02
- Standard fleet synchronization and maintenance.

0.0.56 — 2026-09-02
- Standard fleet synchronization and maintenance.

0.0.55 — 2026-08-25
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/canadian-news/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/canadian-news/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/canadian-news)
- [Support](https://www.reddit.com/r/grantdb)