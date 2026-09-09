# Pinned Menuboard

Category: Moderation  
Version: v0.0.66  
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
0.0.66 — 2026-09-09
- Standard fleet synchronization and maintenance.

0.0.65 — 2026-09-09
- Fix: Align `@devvit/server` and `@devvit/web/server` entrypoint module resolution in `tools/build.cjs` to eliminate dual `AsyncLocalStorage` instances and prevent `No context found` runtime crashes on menu item presses.
- Reliability: Add structured lifecycle logging to `serverOnRequest` for incoming menu and webview requests.

0.0.64 — 2026-09-09
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/pinned-menuboard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/pinned-menuboard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/pinned-menuboard)
- [Support](https://www.reddit.com/r/grantdb)