# RateGuard

Category: Moderation  
Version: v0.0.8  
Visibility: Public  
Summary: Dedicated submission-frequency & posting-cadence gatekeeper for Reddit.

## Overview
Dedicated submission-frequency & posting-cadence gatekeeper for Reddit.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/rate-guard-flowchart.png)

## Key Features
- Not documented yet.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- GuardHub: RateGuard Settings: Configure posting frequency limits and cooldowns. (Location: subreddit)

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/server/index.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- appEnabled: Enable RateGuard (boolean, default: true). Master toggle to enable or pause RateGuard posting frequency limits.
- appMode: App Enforcement Mode (select, default: dry_run). App Enforcement Mode
- minGapDays: Time Between Posts (Days) (number, default: 0). Minimum required days between consecutive user submissions (e.g. 2 = user can only post once every 2 days). Set to 0 if using minutes cooldown below.
- minGapMinutes: Minimum Gap Cooldown (Minutes) (number, default: 120). Minimum required time in minutes between consecutive user submissions (e.g. 120 = 2 hours, 1440 = 1 day, 2880 = 2 days). 0 = disabled.
- maxPosts24h: Rolling 24-Hour Post Cap (number, default: 3). Maximum posts allowed per user in a 24-hour rolling window. 0 = disabled.
- burstMaxPosts: Burst Post Cap (number, default: 3). Maximum posts allowed within the burst window.
- burstWindowMinutes: Burst Window (Minutes) (number, default: 5). Window size in minutes for burst detection (e.g. 5 minutes).
- exemptMods: Exempt Subreddit Moderators (boolean, default: true). Exempt subreddit moderators from all rate limits.
- exemptApproved: Exempt Approved Contributors (boolean, default: true). Exempt approved submitters from all rate limits.
- exemptFlairs: Exempt Post Flairs (string, default: ). Comma-separated list of post flair names exempt from rate limits (e.g. "Megathread, Announcement").

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

## Setup and Usage
- Install: Add Rate Guard to your subreddit through the Reddit App Directory.
- Configure: Open Mod Tools > App Settings > Rate Guard.
- Set Cadence: Configure your time between posts (in days or minutes), 24-hour rolling cap, and burst limit thresholds.
- Save: The cadence engine applies immediately to all incoming community posts.
- No external servers or complicated bot hosting required. Clean, automated rate limiting inside Reddit.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.8 — 2026-09-02
- Standard fleet synchronization and maintenance.

0.0.7 — 2026-08-31
- Standard fleet synchronization and maintenance.

0.0.6 — 2026-08-27
- Add minGapDays multi-day cooldown and fix blocks manifest

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/rate-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/rate-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/rate-guard)
- [Support](https://www.reddit.com/r/grantdb)