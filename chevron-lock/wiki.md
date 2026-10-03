# Chevron Lock

Category: Interactive  
Version: v0.0.14  
Visibility: Unlisted  
Summary: Stargate-inspired 7-chevron dialing console puzzle game.

## Overview
Stargate-inspired 7-chevron dialing console puzzle game.

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
- Hashes (structured records & alias indices)
- Sorted Sets (time-series audit logs)
- Key patterns: node:http, chevlock:daily

## Setup and Usage
- Install: Add Chevron Lock to your subreddit via the Devvit developer platform.
- Launch Post: Open the subreddit Moderator Menu and select "Create Chevron Lock Post"**.
- Configure Options: The post embeds an interactive dialing console directly in your community feed.
- Deploy & Compete: Community members dial gate addresses, maintain stability, and compete for top operator rankings.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.14 — 2026-10-03
- Standard fleet synchronization and maintenance.

0.0.13 — 2026-09-20
- Standard fleet synchronization and maintenance.

0.0.12 — 2026-09-15
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/chevron-lock/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/chevron-lock/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/chevron-lock)
- [Support](https://www.reddit.com/r/grantdb)