# Wiki-Guard

Category: Moderation  
Version: v0.0.2  
Visibility: Unlisted  
Summary: Mobile-friendly Reddit wiki editor for subreddit moderators.

## Overview
Mobile-friendly Reddit wiki editor for subreddit moderators.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/wiki-guard-flowchart.png)

## Key Features
- Zero-Friction Page Navigation: Quickly filter and locate nested wiki pages (e.g. `rules`, `faq`, `resources/setup`).
- Preserved Source of Truth: The raw Markdown text is preserved verbatim without destructive HTML conversion or stripping.
- Version Awareness: Automatically checks whether your subreddit supports Reddit's Wiki V2 platform, while supporting legacy V1 subreddits seamlessly.
- Granular Page Settings: Manage whether pages are listed in the subreddit index and enforce subreddit or moderator-only permission levels.

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
- Approves Content: Yes — Approves content.
- Removes or Filters Content: Yes — Removes or filters non-compliant submissions.
- Dispatches Modmail Alerts: No — Does not send modmail notifications.
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Key patterns: node:http

## Setup and Usage
- Install App: Install Wiki-Guard to your subreddit from the Reddit Developer portal.
- Open Portal: From your subreddit menu, select Wiki-Guard: Subreddit Wiki Editor.
- Browse Pages: View your community's active wiki pages, search existing paths, or tap Create New Page.
- Draft & Save: Edit Markdown content, verify using the Preview tab, and commit your changes instantly.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.2 — 2026-09-21
- Standard fleet synchronization and maintenance.

0.0.1 — 2026-09-20
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/wiki-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/wiki-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/wiki-guard)
- [Support](https://www.reddit.com/r/grantdb)