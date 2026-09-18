# Pinned Menuboard

Category: Moderation  
Version: v0.0.79  
Visibility: Public  
Summary: A centralized menu board for pinned posts

## Overview
A centralized menu board for pinned posts

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/pinned-menuboard-flowchart.png)

## Key Features
- Not documented yet.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- Not documented yet.

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- No custom app settings.

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
- Key patterns: node:http

## Setup and Usage
- Install: Add Pinned Menuboard to your subreddit through the Reddit App Directory.
- Generate Board: Select Generate Pinned Menuboard from Subreddit Mod Tools.
- Feature Threads: Open any post menu (`...`) and click Toggle on Menuboard, or use the in-webview Customize panel.
- Tune Settings: Click Customize in the top-right corner of the board to set your preferred theme, title, and slot count.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.79 — 2026-09-18
- Standard fleet synchronization and maintenance.

0.0.79 — 2026-09-17
- UX & Compliance: Add button-based pagination (4 cards per page with Prev/Next buttons) to eliminate inline scroll traps and fully adhere to Reddit's inline app review guidelines.
- UX & Compliance: Implement fleet-standard floating 48px page scroll controls with fine-tuned 48px step-scroll and continuous long-press.
- UX: Add swipe-drag detection on cards to prevent accidental post navigation while swiping in Reddit mobile feeds.

0.0.78 — 2026-09-16
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/pinned-menuboard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/pinned-menuboard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/pinned-menuboard)
- [Support](https://www.reddit.com/r/grantdb)