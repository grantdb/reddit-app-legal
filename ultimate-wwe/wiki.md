# Ultimate WWE Hub

Category: Interactive  
Version: v0.0.32  
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
0.0.32 — 2026-11-09
- Zero-Scroll Click-Tab Navigation & Interactive Megathread Status Page:
- Added top-level zero-scroll click tabs: `[ MATCHES ]`, `[ CHAMPIONSHIPS ]`, and `[ ROSTER STATS ]` directly within the inline status unit.
- Eliminated internal horizontal scrolling; converted match strip into discrete clickable match chip buttons (`.inline-chip-btn`).
- Added dedicated click-paginated Championships spotlight with champion details, reign days, and historical lineage.
- Added dedicated click-paginated Roster Records card stack (3 per view) with W/L records and win/loss streak tags.
- Tap Toggle Predictions & Interactive Contender Cards:
- Transformed Contender cards into direct 1-tap interactive targets with active glowing highlights and `[ YOUR PICK ]` badges.
- Upgraded `/api/live/predict` server endpoint to support instant pick toggling and switching between contenders.
- Added animated neon pulsing rings (`@keyframes pulse-live-contender`) and gold shimmers to active contenders during live matches.
- Added graphic golden laurel victory stamp (`.winner-card-gold`, `.winner-graphic-badge`) and pick outcome indicators (`[YOUR PICK WON]` / `[YOUR PICK LOST]`) on finished matches.
- Moderator Role Isolation & Realtime Hub Synchronization:
- Restricted full expanded arena mode exclusively to moderators via `[ MOD LIVE CONSOLE ]`, keeping regular fans focused on the live Reddit comment stream.
- Added `updatedHub` payload to realtime `result` broadcasts and implemented `hub_updated` realtime event dispatch so championship belt changes, defense increments, and superstar stats update live on user status cards without requiring a page refresh.
- Resolved duplicate HTML markup in the moderator impromptu add-match tray.

0.0.31 — 2026-11-09
- Devvit SDK v0.15.2 baseline and minor/patch dependency maintenance update.

0.0.30 — 2026-11-08
- Live Megathread Status Page Scoreboard:
- Added horizontal scrolling match card strip (`#inline-card-strip`) rendering all scheduled matches, real-time status pills (`[LIVE]`, `[FINAL]`, `[UPCOMING]`), and 1-tap match switching directly on the status card.
- Added personal picks tracking badge (`#inline-user-picks-badge`, e.g. `MY PICKS: 3-1`).
- Added dynamic superstar sub-stats (`#inline-substat-a/b`) showing season win/loss records, current streaks, and champion designations directly on contender cards.
- Enhanced finished match state with full consensus breakdown (percentage and total vote counts), user pick result tag (`[YOUR PICK WON]` / `[YOUR PICK LOST]`), and post-match 1-5 star ratings directly in feed mode.
- Moderator Match & Wrestler Studio Enhancements:
- Added match card reordering (`[ MOVE UP ]` / `[ MOVE DOWN ]`), match deletion (`[ DELETE MATCH ]`), and event reopening (`[ REOPEN SHOW ]`).
- Added Championship Belt selector dropdown and stipulation quick-chips (`Singles`, `Tag Team`, `Triple Threat`, `Fatal 4-Way`, `Street Fight`, `Steel Cage`, `Ladder`) in match customizer and impromptu match trays.
- Added global superstar autocomplete datalist across all match editor and curator inputs.
- Added Hub Schedule Bulk Import (`[ LOAD FROM HUB SCHEDULE ]`) to instantly populate the live match card from upcoming confirmed PLE/show cards.
- Added in-feed moderator shortcut button (`[ EDIT CARD ]`) visible only to moderators in inline status view.
- Built full Hub Curator Studio (`#hub-mod-bar`) with dedicated editing panels to update championship belt lineages, superstar rosters (W/L, streaks, finishers), and upcoming event fight cards.
- Platform & Realtime Reliability:
- Canonical Devvit realtime subscription using `@devvit/web/client` connection semantics and fixed redis channel naming `wwe-show-${showId}`.
- Replaced native `alert()` modal dialogs with non-blocking inline transient toasts to prevent webview thread freezes.
- Added champion defense counter auto-increment upon successful title defense finishes.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/ultimate-wwe/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/ultimate-wwe/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/ultimate-wwe)
- [Support](https://www.reddit.com/r/grantdb)