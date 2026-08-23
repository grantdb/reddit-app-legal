# SG-1 Responder

Category: Stargate  
Version: v0.0.61  
Visibility: Public  
Summary: New Stargate-themed responder application. Under development.

## Overview
New Stargate-themed responder application. Under development.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/sg1-responder-flowchart.png)

## Key Features
- Contextual Triggers: Intelligently monitors both new submissions and comment threads for specific franchise-themed keywords and quotes.
- Automated Interaction: Automatically delivers canonically accurate responses and character quotes to surprise and engage users.
- Response Variety: Utilizes a weighted random selection algorithm when multiple responses apply, ensuring that the bot's interactions remain fresh and unpredictable rather than robotic.
- Safety Filters: Built with integrated rate limiting, cooldown timers, and moderator exemptions to ensure the bot adds to the fun without ever becoming spammy or annoying.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- PostSubmit: Delivered by Reddit event router to endpoint /internal/on-post-submit.
- PostCreate: Delivered by Reddit event router to endpoint /internal/on-post-create.
- CommentSubmit: Delivered by Reddit event router to endpoint /internal/on-comment-submit.
- CommentCreate: Delivered by Reddit event router to endpoint /internal/on-comment-create.

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
- Dispatches Modmail Alerts: No — Does not send modmail notifications.
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)

## Setup and Usage
- Install: Add SG-1 Responder to your subreddit via the App Directory.
- Configuration: This app currently requires no manual configuration. Its response library and cooldown timers are hardcoded for optimal engagement out of the box.
- Usage: Simply install the app and watch it interact with your community!

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.61 — 2026-08-15
- Standard fleet synchronization and maintenance.

0.0.60 — 2026-08-04
- Standard fleet synchronization and maintenance.

0.0.59 — 2026-08-04
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/sg1-responder/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/sg1-responder/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/sg1-responder)
- [Support](https://www.reddit.com/r/grantdb)