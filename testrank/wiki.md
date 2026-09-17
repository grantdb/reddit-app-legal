# TestRank

Category: Utility  
Version: v0.0.28  
Visibility: Unlisted  
Summary: Tester recognition and ranking app for r/droidapptesters.

## Overview
Tester recognition and ranking app for r/droidapptesters.

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

- enableOpOnboardingModmail: Enable OP Onboarding Modmail (boolean, default: true). Send guidance modmail to post authors when a new testing thread is submitted
- requirePostFlair: Require Post Flair for Testing Eligibility (boolean, default: true). Only onboard posts that have a post flair
- pointsHelpfulFeedback: Points: Helpful Feedback (number, default: 10). XP awarded for general helpful feedback comments
- pointsRegisteredTester: Points: Registered Tester (number, default: 5). XP awarded when a user signs up or registers as a tester
- pointsBugFound: Points: Bug Found (number, default: 25). XP awarded for verified bug reports
- pointsRetest: Points: Fix Verified (number, default: 30). XP awarded for verified bug fix confirmations

## Automation Capabilities
- Submits Automated Comments: Yes — Posts automated comments on target submissions.
- Attaches Removal Notes: No — Does not attach removal notes.
- Approves Content: No — Does not approve content.
- Removes or Filters Content: Yes — Removes or filters non-compliant submissions.
- Dispatches Modmail Alerts: Yes — Sends modmail notifications.
- Updates User or Post Flair: Yes — Updates post or user flair based on rules.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Sorted Sets (time-series audit logs)
- Key patterns: node:http, tr:dashboard_post_url:global, tr:leaderboard_post_url:global

## Setup and Usage
- Install App: Install TestRank to your subreddit from the Reddit App Directory.
- Configure Settings: Adjust point weights and onboarding modmail rules via Mod Tools -> Apps -> testrank -> Settings.
- Generate Leaderboard Post: Open the subreddit overflow menu (`...`) and click Create TestRank Leaderboard Post to provision the pinned community board.
- Reward & Rank: Developers click comment menus on helpful replies to confirm points and immediately trigger leaderboard and flair updates.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.28 — 2026-09-17
- Standard fleet synchronization and maintenance.

0.0.27 — 2026-09-17
- Tuning: Bumped "Fix Verified" reward to 30 points across all action constants, settings, comment menus, dashboard, and documentation to position it as the highest-value tester recognition tier.
- Fix: Resolved issue where floating scroll buttons (FABs) stopped scrolling after only a few lines by locking pointer capture (`setPointerCapture`), removing button scale transforms during active state, applying `touch-action: none`, and switching to continuous deterministic scrolling.

0.0.26 — 2026-09-17
- Feature: Added new "Registered Tester (+5 pts)" action category for quick confirmation of community members who join Google Groups, opt into closed tests, or install app builds.
- Feature: Added "Mark Registered Tester" comment context menu action in `devvit.json` and `/internal/menu/comment-registered`.
- Feature: Added "Registered Recruit" badge unlocked on first registered tester award.
- UX: Added 4th stat column for "Registered" testers on user profiles and live post awards summary.
- Config: Added `pointsRegisteredTester` installation setting (default: 5 pts).

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/testrank/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/testrank/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/testrank)
- [Support](https://www.reddit.com/r/grantdb)