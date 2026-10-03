# SG Team Dispatch

Category: Interactive  
Version: v0.0.7  
Visibility: Unlisted  
Summary: Replayable Stargate SG-1 inspired tactical mission command game.

## Overview
Replayable Stargate SG-1 inspired tactical mission command game.

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
- Key patterns: node:http, sgtd:daily

## Setup and Usage
- Install: Add SG Team Dispatch to your subreddit from the Reddit Developer portal or app directory.
- Launch Post: Open the subreddit Moderator Menu and select "Create SG Team Dispatch Post"**.
- Configure Options: The post embeds an interactive tactical mission command console directly in your community feed.
- Deploy & Compete: Subreddit members assemble squads, deploy offworld, and compete for top commander rankings.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.7 — 2026-10-03
- Standard fleet synchronization and maintenance.

0.0.6 — 2026-09-15
- Standard fleet synchronization and maintenance.

0.0.5 — 2026-09-02
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/sgteam-dispatch/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/sgteam-dispatch/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/sgteam-dispatch)
- [Support](https://www.reddit.com/r/grantdb)