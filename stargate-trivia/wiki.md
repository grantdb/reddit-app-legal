# Stargate Trivia

Category: Interactive  
Version: v0.0.124  
Visibility: Public  
Summary: Interactive trivia engine with rich UI and global leaderboards.

## Overview
Interactive trivia engine with rich UI and global leaderboards.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/stargate-trivia-flowchart.png)

## Key Features
- Curated Content: Features a proprietary library of unique, canonical trivia questions ensuring that hardcore fans are challenged.
- Persistent Leaderboards: Encourages long-term community engagement by tracking high scores and milestones directly on the event post.
- Seamless Experience: A custom-designed, low-latency interface that ensures perfect mobile and desktop rendering without leaving the Reddit app.
- Autonomous Game Logic: Automatically handles answer validation, scoring, and session management—no moderator oversight required once the event is launched.

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
- Launch Event: Open the Mod Menu on your subreddit and select Create Stargate Trivia Post.
- Autonomous Execution: The interactive game post will automatically handle player sessions, answer validation, and score tracking with zero ongoing maintenance.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.124 — 2026-08-27
- Standard fleet synchronization and maintenance.

0.0.124 — 2026-08-27
- Standard fleet synchronization and maintenance.

0.0.123 — 2026-08-15
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/stargate-trivia/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/stargate-trivia/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/stargate-trivia)
- [Support](https://www.reddit.com/r/grantdb)