# Ultimate WWE Hub

Category: Interactive  
Version: v0.0.24  
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
- Run the Show: Use the moderator console to start matches and declare winners as the action unfolds!

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.24 — 2026-10-24
- Canonical Webview & Scrolling Standard v2.1 & Viewport Refinement:
- Replaced arbitrary inline max-height constraints (`max-height: 512px` and `@media (max-width: 480px) { max-height: 360px }`) with mode-aware `html.app-inline-mode .inline-summary-view { height: 100%; max-height: 100%; overflow: hidden; display: flex; flex-direction: column; gap: 8px; }`.
- Replaced negative `:not(.app-expanded-mode)` selectors with canonical `html.app-inline-mode` and `html.app-expanded-mode` selectors across markup and styles.
- Implemented progressive vertical height disclosure: `@media (max-height: 440px)` hides secondary guidance text and rating row; `@media (max-height: 380px)` hides compact chants and guidance container while preserving show badge/status, current match contenders, and primary Vote/Cheer actions.
- Enforced `flex-shrink: 0 !important;` on `[ VIEW FULL ARENA ]` CTA button, header rows, and action button rows so interactive controls are never clipped or unreachable on constrained mobile feed viewports.
- Standardized viewport template to `` and synced client runtime mode listeners.
- Strictly Optional Expanded Mode (Zero Auto-Launch):
- Primary inline Live Match Summary (`#inline-summary-view`) is the default, non-scrolling feed experience for Raw and SmackDown live megathreads.
- Users can vote, cheer, rate (1-5 stars), see live match momentum, and scroll freely down to Reddit's native Live-sorted comment feed.
- Eliminated all automatic calls to `requestExpandedMode()` (never triggers on app load, splash tap, match start, realtime update, or post creation).
- Renamed launch CTA to `[ VIEW FULL ARENA ]` (`aria-label="Open full arena view"`) as a secondary, strictly user-gesture entry into expanded arena mode.
- Added always-visible `[ BACK TO COMMENTS ]` (`aria-label="Return to post comments"`) in expanded top bar calling `exitExpandedMode()` to return users to inline summary.
- Moved detailed content (Tale of the Tape, full chant soundboard, pyro/celebration stage, and moderator console) to expanded mode.
- Ensured tap targets are >= 44px tall and respected `prefers-reduced-motion: reduce`.
- Data Deletion & Retention Hardening:
- Hardened `onPostDelete` trigger handler to resolve trusted `showId` from post bootstrap metadata and delete all user-linked data (predictions, ratings, momentum, rate-limit keys, show users index).
- Deleted live match state, realtime channel references, and redacted audit entries.
- Unindexed deleted shows from `wwe:shows:index`, `wwe:shows:raw:index`, and `wwe:shows:smackdown:index`.
- Reduced post metadata to an idempotent minimal tombstone (`postId`, `showId`, `createdAt`, `deletedAt`) with 30-day TTL.
- Applied 30-day TTL (`USER_DATA_TTL_SECONDS = 2592000`) across all per-user records and audit sets.
- Hashed actor references (`actorRef: "actor_"`) in audit logs to prevent plain username retention.
- Event Archival & Multi-Show Isolation:
- Enforced show-scoped Redis key schema (`wwe:show:`, `:matches`, `:match:`, `:predictions:`, `:ratings:`, `:audit`, and `wwe:live:channel:`) alongside show indexes (`wwe:shows:index`, `wwe:shows:raw:index`, `wwe:shows:smackdown:index`), strictly eliminating all global show state keys.
- Implemented `resolveTrustedShow` validation helper to verify post bootstrap metadata against requested `showId` and reject cross-show tampering (HTTP 400).
- Completed show lifecycle transitions: sets `LiveEventShow.status = 'completed'` and `endedAt` to UTC ISO timestamp when all matches finish or moderator executes `complete_show`.
- Inline completed show state: renders `"RAW COMPLETE / Final results available below"` in feed summary and locks all live interactions (predictions, cheers, chants, ratings return 400).
- Built compact post-show recap card: highlights Match of the Night based on highest average star rating, evaluates community prediction consensus accuracy percentage, displays championship title changes, and lists all official match results.
- New weekly event behavior: generates date-scoped unique `showId` (e.g. `raw-2026-11-03`), creates fresh custom post with `suggestedCommentSort: 'LIVE'`, and initializes independent Redis show state without resetting, modifying, or deleting prior completed shows.
- Added Devvit `onPostDelete` trigger handler to remove transient post bootstrap metadata while preserving archived show records for community history.
- Architectural Redesign & Streamlined 3-Post Engine (Phase 1-3 Foundation):
- Streamlined post creation into 3 dedicated custom post types: WWE Belts & Stats Hub, Monday Night Raw Live Megathread, and Friday Night SmackDown Live Megathread.
- Implemented native Reddit Live comments with `suggestedCommentSort: 'LIVE'` on Raw and SmackDown posts, eliminating comment duplication in the webview.
- Integrated Devvit realtime channel broadcasting (`LiveBroadcast`) for instantaneous client state synchronization without polling.
- Built Before vs. During match lifecycle engine: Pre-match winner prediction, crowd momentum tug-of-war, generic crowd chant soundboard, and 1–5 star match ratings.
- Established canonical moderator action `[ START MATCH ]` and `[ DECLARE WINNER ]` with golden victory celebration.
- Server-side cached moderator validation and rate limits for momentum cheers and crowd reactions.
- High-impact arena visual system: Titan-Tron scanlines, Crimson Red Raw neon, Electric Blue SmackDown spotlights, and Championship Gold shimmer.

0.0.23 — 2026-10-17
- Standard fleet synchronization and maintenance.

0.0.23 — 2026-10-17
- Mobile Header Text Containment & Viewport Protection: Fixed vertical layout blowouts on mobile devices:
- Added `.inline-title-container` with strict `min-width: 0; flex: 1; overflow: hidden;` containment and `white-space: nowrap; text-overflow: ellipsis;` on `.inline-brand-title`.
- Hidden redundant `.inline-brand-sub` on narrow mobile screens (`@media (max-width: 480px)`), capping header height strictly at 36px and eliminating 10-line text wrapping.
- Added `flex-shrink: 0;` to `.btn-primary-expand` and tightened launchpad vertical gap spacing so the primary "ENTER WWE ARENA (EXPANDED MODE)" CTA button remains 100% visible and clickable within the 512px feed viewport.
- Added title tooltip attributes on title and subtitle elements in `src/client/main.ts` for full text accessibility.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/ultimate-wwe/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/ultimate-wwe/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/ultimate-wwe)
- [Support](https://www.reddit.com/r/grantdb)