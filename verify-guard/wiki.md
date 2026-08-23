# VerifyGuard

Category: Security  
Version: v0.0.4  
Visibility: Public  
Summary: Configurable multi-tier verification engine for user trust, age, and role verification.

## Overview
Configurable multi-tier verification engine for user trust, age, and role verification.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/verify-guard-flowchart.png)

## Key Features
- Not documented yet.

## Permissions Used
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- GuardHub: VerifyGuard Dashboard: Open the verification moderation dashboard. (Location: subreddit)
- GuardHub: Create Verification Post: Create a community user verification launcher post. (Location: subreddit)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- daily-expiration-cron: Pending Queue (${queue.length}) (success, default: -). Pending Queue (${queue.length})

## Automation Capabilities
- Submits Automated Comments: No — Does not submit automated comments.
- Attaches Removal Notes: No — Does not attach removal notes.
- Approves Content: No — Does not approve content.
- Removes or Filters Content: Yes — Removes or filters non-compliant submissions.
- Dispatches Modmail Alerts: No — Does not send modmail notifications.
- Updates User or Post Flair: Yes — Updates post or user flair based on rules.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Hashes (structured records & alias indices)
- Sorted Sets (time-series audit logs)

## Setup and Usage
- Install: Add Verify Guard to your subreddit through the Reddit App Directory.
- Configure: Open GuardHub: VerifyGuard Dashboard from Subreddit Mod Tools.
- Launch Post: Click GuardHub: Create Verification Post to create your community intake post.
- Activate: Set your desired verification tiers to begin welcoming verified members.
- No modmail clutter or sensitive data exposure. Streamlined community verification directly in Reddit.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.4 — 2026-08-15
- Standard fleet synchronization and maintenance.

0.0.3 — 2026-08-10
- Standard fleet synchronization and maintenance.

0.0.2 — 2026-08-10
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/verify-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/verify-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/verify-guard)
- [Support](https://www.reddit.com/r/grantdb)