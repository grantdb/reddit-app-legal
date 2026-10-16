# RescueGuard

Category: Moderation  
Version: v0.0.24  
Visibility: Public  
Summary: Subreddit post-discovery & manual spotlight moderation engine for Reddit.

## Overview
Subreddit post-discovery & manual spotlight moderation engine for Reddit.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/rescue-guard-flowchart.png)

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
- Submits Automated Comments: Yes — Posts automated comments on target submissions.
- Attaches Removal Notes: No — Does not attach removal notes.
- Approves Content: Yes — Approves content.
- Removes or Filters Content: Yes — Removes or filters non-compliant submissions.
- Dispatches Modmail Alerts: No — Does not send modmail notifications.
- Updates User or Post Flair: Yes — Updates post or user flair based on rules.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Key patterns: node:http

## Setup and Usage
- Install: Add RescueGuard to your subreddit through the Reddit App Directory.
- Configure: Open Mod Tools > App Settings > RescueGuard.
- Set Thresholds: Configure your batch size, minimum post age, lookback days, deduplication strategy, and spotlight flair/comment text.
- Launch Review: Open the subreddit menu and select GuardHub: RescueGuard Review Hub.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.24 — 2026-10-16
- Standard fleet synchronization and maintenance.

0.0.24 — 2026-10-15
- Adopt mod360pro canonical expanded UI architecture to eliminate mobile feed scrolling defects:
- Added dedicated zero-scroll Inline Launch Card for feed view (`#inline-launch-view`):
- Strictly bounded height (max 512px) with `overflow: hidden; touch-action: pan-y;` ensuring natural, untrapped feed gesture chaining.
- Status card with discovery metrics (candidates awaiting review, lookback window, deduplication guard, spotlight action).
- Prominent `Launch Review Hub` primary action button calling `requestExpandedMode(e, 'expanded')`.
- Registered `"expanded": { "entry": "index.html" }` entrypoint in `devvit.json`.
- Upgraded Expanded Mode Review Hub (`#expanded-console-view`):
- Full cockpit with two-tier GuardHub header, theme toggle button, and inline return button calling `exitExpandedMode(e)`.
- tab console (Overview, Review Queue with 3-per-page button pagination, Spotlight History, Settings).
- Floating 48px page scroll FABs (▲ and ▼) with 48px fine-tuned steps and continuous hold.
- Dual-theme support (Dark and Light) with persisted settings.
- Purged obsolete Blocks legacy files (`src/main.ts`, `src/scanner.ts`).
- Added client compilation with esbuild in `tools/build.ts` bundling `@devvit/client`.
- Enforced fleet-wide Zero-Emoji Policy: replaced unicode emojis across HTML, CSS, JS, and Markdown with SVGs and styled badges.

0.0.23 — 2026-09-20
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/rescue-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/rescue-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/rescue-guard)
- [Support](https://www.reddit.com/r/grantdb)