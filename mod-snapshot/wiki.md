# Mod Snapshot

Category: Archival  
Version: v0.0.81  
Visibility: Public  
Summary: Professional-grade subreddit configuration backup. Delivers comprehensive archival snapshots and best-effort app discovery to Modmail.

## Overview
Professional-grade subreddit configuration backup. Delivers comprehensive archival snapshots and best-effort app discovery to Modmail.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/mod-snapshot-flowchart.png)

## Key Features
- Not documented yet.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- Generate Mod Snapshot: Moderator menu action (Location: subreddit)

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- daily_limit: Daily Manual Snapshot Limit (select, default: 24). Daily Manual Snapshot Limit

## Automation Capabilities
- Submits Automated Comments: No — Does not submit automated comments.
- Attaches Removal Notes: No — Does not attach removal notes.
- Approves Content: No — Does not approve content.
- Removes or Filters Content: Yes — Removes or filters non-compliant submissions.
- Dispatches Modmail Alerts: Yes — Sends modmail notifications.
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)

## Setup and Usage
- Install: Add Mod Snapshot to your subreddit through the Reddit App Directory.
- Configure Settings: Open Mod Tools > App Settings > Mod Snapshot to review snapshot preferences.
- Run Backup: Select Generate Mod Snapshot from Subreddit Mod Tools to create your first archive.
- Verify: Open modmail to inspect your complete, structured backup document.
- No external backup servers or manual exports required. Reliable community disaster recovery inside Reddit.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.81 — 2026-09-02
- Standard fleet synchronization and maintenance.

0.0.80 — 2026-08-15
- Standard fleet synchronization and maintenance.

0.0.79 — 2026-08-02
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/mod-snapshot/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/mod-snapshot/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/mod-snapshot)
- [Support](https://www.reddit.com/r/grantdb)