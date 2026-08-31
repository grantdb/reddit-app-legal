# Pinned Menuboard

Category: Moderation  
Version: v0.0.62  
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
- Removes or Filters Content: No — Does not remove or filter content.
- Dispatches Modmail Alerts: No — Does not send modmail notifications.
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Key patterns: node:http

## Setup and Usage
- Install: Add Pinned Menuboard to your subreddit through the Reddit App Directory.
- Generate Board: Select Generate Pinned Menuboard from Subreddit Mod Tools and sticky the resulting post.
- Feature Content: Open any post and select Toggle on Menuboard to add it to an open slot.
- Customize: Adjust board headers and styling preferences in App Settings anytime.
- No markdown link tables to update manually. Visual community navigation directly inside your feed.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.62 — 2026-08-31
- Standard fleet synchronization and maintenance.

0.0.61 — 2026-08-15
- Standard fleet synchronization and maintenance.

0.0.60 — 2026-08-04
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/pinned-menuboard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/pinned-menuboard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/pinned-menuboard)
- [Support](https://www.reddit.com/r/grantdb)