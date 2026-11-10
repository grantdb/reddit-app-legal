# Ultimate WWE Hub

Category: Interactive  
Version: v0.0.37  
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
- AppUpgrade: Delivered by Reddit event router to endpoint /internal/on-app-install.
- PostDelete: Delivered by Reddit event router to endpoint /internal/on-post-delete.

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
- Key patterns: node:http, wwe:hub:sub_123, wwe:show:raw-101, wwe:show:raw-101:matches, wwe:show:raw-101:match:m-1, wwe:show:show-1:predictions:wrestlingfan:m-1

## Setup and Usage
- Install: Add Ultimate WWE Hub to your subreddit via the Reddit Developer portal.
- Launch Anchor Hub: From your subreddit menu (`...`), select Create WWE Belts & Stats Hub Post and pin it as a community anchor.
- Deploy Live Megathread: On broadcast night, select Create Monday Night Raw Live Megathread or Create Friday Night SmackDown Live Megathread.
- Run the Show: Use the moderator console to start matches, reorder the card, and declare winners as the action unfolds!

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.37 — 2026-11-09
- Active Crowd Chants During Winner Celebration & Match Reset:
- Allowed chant reactions to be processed on both server and client during the post-match 2-minute celebration window.
- Fixed client click guard and re-enabled chant buttons throughout celebration countdown.
- In `reset_match` and `start_match`, broadcast full `show_updated` payload so connected clients immediately clear stale winner IDs, finish states, and re-arm crowd chants cleanly.
- Top Subtabs Navigation Bar Hidden:
- Set `#inline-subtabs-row` to `display: none !important;` to reclaim 44px of vertical screen real estate for match action, while preserving all subtab HTML markup and TypeScript controllers intact for future app feature upgrades.
- Single Unified Match Victory Takeover Card:
- Replaced disjointed multiple bottom winner blocks with a single unified Match Victory Takeover Card (`#inline-victory-takeover`).
- Seamlessly integrates floating sparks, champion winner headline, celebration chant soundboard with real-time countdown clock (`RECAP IN 01:51`), and prediction consensus ribbon into a single cohesive bottom takeover.

0.0.36 — 2026-11-09
- High-Intensity Flashing Winner Celebration (`WINNER!!`):
- Upgraded winner badge to bold `WINNER!!` with high-frequency golden strobe aura (`@keyframes winner-badge-flash`).
- Added radiant Champion Celebration Strobe (`@keyframes winner-celebration-strobe`) on the victor's contender card with glowing gold name typography and dimmed loser card state.
- Energetic Flashing Live Match Header:
- Added dynamic high-intensity broadcast strobe animation (`@keyframes live-header-raw-flash` and `@keyframes live-header-sd-flash`) to the live brand header badge (`RAW LIVE` / `SMACKDOWN LIVE`) whenever a match is actively in progress.
- Added vibrant neon strobe pulse (`@keyframes live-chip-strobe`) to the active match chip (`M1 [LIVE]`).
- Zero-Scroll Box Score Cleanup:
- Removed the internal scrollable match result container (`#inline-boxscore-results-list`) from the post-show box score card, eliminating vertical scrollbars and arrows from the feed view in accordance with the Fleet Webview Zero-Scroll standard.

0.0.35 — 2026-11-09
- Minute In-Ring Celebration Window & Auto-Transition:
- When a match concludes, the status page enters an active 2-minute live celebration mode (`[MATCH DECIDED]`) keeping crowd chant buttons active and live countdown clock running (`RECAP IN 01:59`).
- At the end of the 2-minute celebration window, the card automatically transitions into the full celebratory Pyro Victory Banner.
- Spectacle Pyro Victory Banner on User Status Page:
- Added full celebratory Pyro Victory Banner with 6 floating golden spark embers (`.pyro-spark spark-1...6`), golden strobe aura, match duration badge (`OFFICIAL DURATION`), and fan consensus accuracy ribbon (`100% of fans predicted this win`).
- Streamlined User View & Star Rating Removal:
- Removed 5-star rating rows from the status page, maximizing vertical headroom for contender cards and celebratory graphics.
- Superstars Tale of the Tape & Center Title Belt:
- Added finisher pills (`Finisher: Spear`, `Finisher: Uso Splash`) on contender cards.
- Added glowing gold championship title line (`[TITLE] `) beneath the central VS circle.
- Mod View Performance Streamlining:
- Stripped decorative pyro particles and strobe animations from the Expanded Mod View for a fast, high-contrast operational cockpit.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/ultimate-wwe/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/ultimate-wwe/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/ultimate-wwe)
- [Support](https://www.reddit.com/r/grantdb)