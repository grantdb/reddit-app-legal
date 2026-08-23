# Gate Defender

Category: Interactive  
Version: v0.0.98  
Visibility: Public  
Summary: Community security gatekeeper. React Webview-based entry validation.

## Overview
Community security gatekeeper. React Webview-based entry validation.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/gate-defender-flowchart.png)

## Key Features
- High-Velocity Survival Mechanics: Fast-paced, responsive arcade gameplay that relies on quick reflexes and pattern recognition.
- Persistent Global Leaderboards: Features a real-time "Top 10" ranking system embedded directly in the post to encourage recurring community engagement and rivalry.
- Mobile-Optimized Interface: Custom-built and rigorously tested to ensure smooth performance and touch controls across all Reddit mobile platforms and desktop web.
- Interactive Onboarding: Features a pre-game splash screen providing swift, easy-to-understand tutorial instructions so players can jump right in.
- Moderator-Initiated Launch: Simple, one-click deployment via the Subreddit Moderator Menu makes it incredibly easy for mod teams to schedule gaming events or weekend community threads.

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
- Sorted Sets (time-series audit logs)
- Key patterns: node:http, node:events

## Setup and Usage
- Install: Add Gate Defender to your subreddit via the App Directory.
- App Settings: (Optional) Use the subreddit's App Settings to tweak gameplay difficulty multipliers if your community wants a harder challenge.
- Usage: To start a community event, simply open the Mod Menu anywhere in your subreddit and select the "Launch Gate Defender" action to spawn a new game post.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.98 — 2026-08-15
- Standard fleet synchronization and maintenance.

0.0.97 — 2026-07-27
- Server: Standardized error status code handling and response structure.

0.0.96 — 2026-07-24
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/gate-defender/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/gate-defender/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/gate-defender)
- [Support](https://www.reddit.com/r/grantdb)