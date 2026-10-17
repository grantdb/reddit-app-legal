# Ultimate WWE Hub

Category: Interactive  
Version: v0.0.23  
Visibility: Unlisted  
Summary: Interactive WWE live event mega-thread engine with match cards, pick 'em prediction game, and dual leaderboards.

## Overview
Interactive WWE live event mega-thread engine with match cards, pick 'em prediction game, and dual leaderboards.

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
- Hashes (structured records & alias indices)
- Sorted Sets (time-series audit logs)
- Key patterns: node:http

## Setup and Usage
- Install: Add Ultimate WWE Hub to your subreddit via the Reddit Developer portal or App Directory.
- Launch Pinned Hub Posts: From your subreddit menu (`...`), deploy the Superstar Stats, Records & Belts Post and Community Prediction & Picking Board as pinned community anchors.
- Deploy Live Event Thread: On event night, select Create WWE Live Event Thread to launch the show mega-thread with live match cards, community pick consensus, and live chat.
- Score & Crown Champions: Declare winners as the broadcast unfolds and click Score Event Results to update community rankings!

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.23 — 2026-10-17
- Standard fleet synchronization and maintenance.

0.0.23 — 2026-10-17
- Mobile Header Text Containment & Viewport Protection: Fixed vertical layout blowouts on mobile devices:
- Added `.inline-title-container` with strict `min-width: 0; flex: 1; overflow: hidden;` containment and `white-space: nowrap; text-overflow: ellipsis;` on `.inline-brand-title`.
- Hidden redundant `.inline-brand-sub` on narrow mobile screens (`@media (max-width: 480px)`), capping header height strictly at 36px and eliminating 10-line text wrapping.
- Added `flex-shrink: 0;` to `.btn-primary-expand` and tightened launchpad vertical gap spacing so the primary "ENTER WWE ARENA (EXPANDED MODE)" CTA button remains 100% visible and clickable within the 512px feed viewport.
- Added title tooltip attributes on title and subtitle elements in `src/client/main.ts` for full text accessibility.

0.0.21 — 2026-10-17
- Webview Scrolling & FAB Engine Alignment: Aligned `public/index.css` and `src/client/main.ts` with canonical `mod360pro` architecture:
- Scoped `height: 100%; overflow: hidden !important;` strictly to `body:not(.app-expanded-mode)` while unlocking full vertical scrolling on `body.app-expanded-mode`.
- Resolved container metric false-positives in `getScrollMetrics()` to ensure window/document root scroller is prioritized when `.app-root` expands with content.
- Replaced unicode glyphs (`◀`, `▶`, `▲`, `▼`) with crisp inline SVGs across navigation tab steppers and floating page scroll FABs conforming to fleet Zero-Emoji Policy.
- Fixed pointer hold engine in `bindNavBtn` and `bindBtn` to support single-step tap execution on `onClick` without getting suppressed by gesture cancelation.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/ultimate-wwe/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/ultimate-wwe/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/ultimate-wwe)
- [Support](https://www.reddit.com/r/grantdb)