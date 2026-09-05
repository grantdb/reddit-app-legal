# AutoMod Easy

Category: Moderation  
Version: v0.0.138  
Visibility: Public  
Summary: No-code visual rule builder for AutoModerator. Generates and validates YAML configurations automatically.

## Overview
No-code visual rule builder for AutoModerator. Generates and validates YAML configurations automatically.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/automod-easy-flowchart.png)

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

- Harassment Filter: Rule Name (string, default: -). Rule Name
- keywords: Keywords to Ban (comma separated) (string, default: -). Keywords to Ban (comma separated)
- reason: Internal Mod Note (e.g. (string, default: -). Internal Mod Note (e.g.

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
- Key patterns: node:http, automod_easy:meta

## Setup and Usage
- Install: Add AutoMod Easy to your subreddit through the Reddit App Directory.
- Open Trainer: Select AutoMod Easy Trainer from Subreddit Mod Tools.
- Audit Rules: Review the initial health scorecard of your current AutoMod configuration.
- Experiment: Use the Sandbox Lab to test new rules or verify starter templates.
- No scary live-testing mistakes. Safe, visual AutoModerator development inside Reddit.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.138 — 2026-09-05
- Standard fleet synchronization and maintenance.

0.0.137 — 2026-09-02
- Standard fleet synchronization and maintenance.

0.0.136 — 2026-08-24
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/automod-easy/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/automod-easy/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/automod-easy)
- [Support](https://www.reddit.com/r/grantdb)