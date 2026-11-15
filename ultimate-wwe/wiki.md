> [Full User Guide](https://www.reddit.com/r/grantdb/wiki/ultimate-wwe/) | **Technical Reference & Settings Spec**

# Ultimate WWE Hub

Category: Interactive  
Version: v0.0.41  
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
- Submits Automated Comments: Yes — Posts automated comments on target submissions.
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
- Key patterns: node:http, wwe:hub:sub_123, wwe:show:raw-101, wwe:show:raw-101:matches, wwe:show:raw-101:match:m-1, wwe:show:show-1:predictions:wrestlingfan:m-1

## Setup and Usage
- Install: Add Ultimate WWE Hub to your subreddit via the Reddit Developer portal.
- Launch Anchor Hub: From your subreddit menu (`...`), select Create WWE Belts & Stats Hub Post and pin it as a community anchor.
- Deploy Live Megathread: On broadcast night, select Create Monday Night Raw Live Megathread or Create Friday Night SmackDown Live Megathread, then run the show from the Moderator Console.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.41 — 2026-11-15
- Add permissions.reddit.asUser SUBMIT_COMMENT in devvit.json for runAs USER Reddit comment sync, with compensating rollback, idempotency, and atomic Redis hash storage

0.0.40 — 2026-11-15
- Wire bulk_import full-card replacement vs impromptu match mode, revamp [SHOW RECAP], and add reusable live-comments system (preview, 65% drawer, synced standard block)

0.0.39 — 2026-11-09
- Chants Active Lifecycle & Next Match Scoping:
- Scoped chants dynamically to each match: chant soundboard remains active on a finished match until the next match on the card begins (becomes live or finished).
- Main Event / final match retains its victory takeover card and chant soundboard.
- End-of-Show Official Recap & Box Score Tab:
- Removed per-match recap countdown badge and automatic boxscore replacement on individual matches.
- Added dedicated `[SHOW RECAP]` tab to the match strip when the show is completed (`currentShow.status === "completed"`), allowing fans to view the official boxscore and show grade at the end of the show while preserving full match result history.
- Prediction Voting Lock on Match Start:
- Enforced strict closure of prediction picks and voting once a match transitions out of `upcoming` (to `live` or `finished`), hiding action CTAs and disabling contender voting buttons across client and server.
- High-Impact Visual Upgrades:
- Winner contender card features a clean, crisp 2px gold highlight without blinding strobes.
- Big winner victory takeover box pulses gently (`victory-box-pulse`).
- Winner name shimmers with high-contrast metallic gold text gradient (`winner-name-shimmer-fast`).

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/ultimate-wwe/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/ultimate-wwe/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/ultimate-wwe)
- [Support](https://www.reddit.com/r/grantdb)