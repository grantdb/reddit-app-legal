# TestRank

Category: Utility  
Version: v0.0.38  
Visibility: Unlisted  
Summary: Automated community tester recognition, reputation, and leaderboard engine for beta testing subreddits.

## Overview
Automated community tester recognition, reputation, and leaderboard engine for beta testing subreddits.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/testrank-flowchart.png)

## Key Features
- Not documented yet.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- AppInstall: Delivered by Reddit event router to endpoint /internal/on-app-install.
- AppUpgrade: Delivered by Reddit event router to endpoint /internal/on-app-install.
- PostSubmit: Delivered by Reddit event router to endpoint /internal/on-post-submit.
- PostCreate: Delivered by Reddit event router to endpoint /internal/on-post-submit.
- CommentCreate: Delivered by Reddit event router to endpoint /internal/on-comment-create.
- CommentSubmit: Delivered by Reddit event router to endpoint /internal/on-comment-create.

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- onboardingDeliveryMethod: OP Onboarding Delivery Method (select, default: comment). OP Onboarding Delivery Method
- requirePostFlair: Require Testing Post Flair for Onboarding (boolean, default: true). Require Testing Post Flair for Onboarding
- enableOpOnboardingModmail: Enable Onboarding Guidance (boolean, default: true). Enable Onboarding Guidance
- pointsHelpfulFeedback: Points: Helpful Feedback (number, default: 10). XP awarded for general helpful feedback comments
- pointsRegisteredTester: Points: Registered Tester (number, default: 5). XP awarded when a user signs up or registers as a tester
- pointsBugFound: Points: Bug Found (number, default: 25). XP awarded for verified bug reports
- pointsRetest: Points: Fix Verified (number, default: 30). XP awarded for verified bug fix confirmations

## Automation Capabilities
- Submits Automated Comments: Yes — Posts automated comments on target submissions.
- Attaches Removal Notes: No — Does not attach removal notes.
- Approves Content: No — Does not approve content.
- Removes or Filters Content: Yes — Removes or filters non-compliant submissions.
- Dispatches Modmail Alerts: No — Does not send modmail notifications.
- Updates User or Post Flair: Yes — Updates post or user flair based on rules.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Sorted Sets (time-series audit logs)
- Key patterns: node:http, tr:dashboard_post_url:global, tr:leaderboard_post_url:global

## Setup and Usage
- Install App: Install TestRank to your subreddit from the Reddit App Directory.
- Configure Settings: Adjust point weights and onboarding delivery channels via Mod Tools -> Apps -> testrank -> Settings.
- Generate Leaderboard Post: Open the subreddit overflow menu (`...`) and click Create TestRank Leaderboard Post to provision the pinned community board.
- Reward & Rank: Developers click comment menus on helpful replies to confirm points and immediately trigger leaderboard and flair updates.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.38 — 2026-10-23
- Standard fleet synchronization and maintenance.

0.0.38 — 2026-10-23
- Leaderboard Pagination Display Fix: Only display `#pagination-bar` when `totalPages > 1` (aligning with `pinned-menuboard` standard) so single-page periods like Weekly do not display a redundant disabled `1 / 1` pagination bar.
- Desktop Viewport Height Optimization: Eliminated vertical overflow clipping by removing redundant `.info-banner` (reclaiming 50px), reducing desktop card/item padding, and tuning margins to guarantee `#pagination-bar` is 100% visible and unclipped on 4-item leaderboards (Monthly & All-Time).
- Top Page Badge: Added dynamic `#meta-page-badge` in the meta bar to display active page progression alongside refresh status when `totalPages > 1`.

0.0.37 — 2026-10-23
- Leaderboard Pagination & Scroll Fix: Completely removed obsolete floating page scroll buttons (`.mobile-scroll-fab-container` with `#scroll-fab-top` and `#scroll-fab-bottom`) from `leaderboard.html` and `src/client/leaderboard.ts` to eliminate non-functional arrow controls and resolve user confusion.
- Mobile Viewport Budgeting: Budgeted mobile feed height under ≤360px in `leaderboard.html` with compact padding, fine-tuned card typography, and `flex-shrink: 0 !important;` on `#pagination-bar` to guarantee that Prev/Next pagination buttons and page indicators are always fully visible on all mobile viewports.
- Enhanced Touch Safety: Added `pointercancel` and `lostpointercapture` guards to `attachSwipeDragGuard` in `src/client/leaderboard.ts` to ensure consistent tap response without gesture locking on mobile WebViews.
- Console Scroll FAB Visibility Guard: Updated `checkScrollState` in `src/client/index.ts` to dynamically hide floating scroll FABs whenever page content does not overflow (`maxScroll <= 15`).

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/testrank/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/testrank/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/testrank)
- [Support](https://www.reddit.com/r/grantdb)