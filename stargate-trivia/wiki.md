> [Full User Guide](https://www.reddit.com/r/grantdb/wiki/stargate-trivia/) | **Technical Reference & Settings Spec**

# Stargate Trivia

Category: Interactive  
Version: v0.0.133  
Visibility: Public  
Summary: Interactive trivia engine with rich UI and global leaderboards.

## Overview
Interactive trivia engine with rich UI and global leaderboards.

## Key Features
- Not documented yet.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- AppInstall: Delivered by Reddit event router to endpoint /internal/on-app-install.

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
- Sorted Sets (time-series audit logs)
- Key patterns: node:http, node:events

## Setup and Usage
- Install: Add Stargate Trivia to your subreddit via the Reddit App Directory.
- Launch: Open the subreddit menu (`...`) and select Create Stargate Trivia Post.
- Play: Community members tap the post to play and compete on the persistent leaderboard with zero ongoing moderation required.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.133 — 2026-11-24
- Fix Back to Gate Room on expanded leaderboard returning to frozen last question instead of Game Over screen (Dial Again / Leaderboard / Exit), and wire Prev/Next leaderboard pagination

0.0.132 — 2026-11-24
- Fix Redis TxClient zScore NaN bug in onSubmitScore preventing leaderboard high-score saves

0.0.131 — 2026-11-09
- Devvit SDK v0.15.2 baseline and minor/patch dependency maintenance update.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/stargate-trivia/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/stargate-trivia/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/stargate-trivia)
- [Support](https://www.reddit.com/r/grantdb)