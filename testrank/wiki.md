# TestRank

Category: Utility  
Version: v0.0.14  
Visibility: Unlisted  
Summary: Tester recognition and ranking app for r/droidapptesters.

## Overview
Tester recognition and ranking app for r/droidapptesters.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/testrank-flowchart.png)

## Key Features
- Not documented yet.

## Permissions Used
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- AppInstall: Delivered by Reddit event router to endpoint /internal/on-app-install.
- PostSubmit: Delivered by Reddit event router to endpoint /internal/on-post-submit.
- CommentCreate: Delivered by Reddit event router to endpoint /internal/on-comment-create.

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
- Updates User or Post Flair: Yes — Updates post or user flair based on rules.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Sorted Sets (time-series audit logs)
- Key patterns: node:http, tr:dashboard_post_url:global, tr:leaderboard_post_url:global

## Setup and Usage
- Post your app testing thread in the subreddit with an appropriate link flair.
- Review comments from testers. On helpful replies, open the comment menu (`...`) and click:
- Mark Helpful Feedback (+10 pts)
- Mark Bug Found (+25 pts)
- Mark Retest (+15 pts)
- Alternatively, open Open This Post’s TestRank Dashboard from the post overflow menu to view all post commenters and award summary cards.
- To opt out a specific thread from TestRank, comment `!testrank-optout` on your post.
- Test apps shared in the subreddit and leave descriptive feedback.
- Track your cumulative XP, current rank, and unlocked milestone badges directly in the TestRank dashboard.
- Watch your subreddit user flair automatically upgrade as you climb the prestige ladder.
- Select Open TestRank Mod Dashboard from the subreddit menu to inspect real-time weekly/monthly leaderboards, toggle post or user participation, and view the immutable audit log.
- Select Create TestRank Custom Post to generate a pinned public leaderboard post for the community.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.14 — 2026-08-18
- Standard fleet synchronization and maintenance.

0.0.13 — 2026-08-18
- Standard fleet synchronization and maintenance.

0.0.12 — 2026-08-15
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/testrank/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/testrank/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/testrank)
- [Support](https://www.reddit.com/r/grantdb)