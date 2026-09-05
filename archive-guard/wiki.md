# Archive-Guard

Category: Moderation  
Version: v0.0.5  
Visibility: Unlisted  
Summary: Subreddit memory engine that detects recurring discussion topics, clusters repeat questions, and tracks canonical threads.

## Overview
Subreddit memory engine that detects recurring discussion topics, clusters repeat questions, and tracks canonical threads.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/archive-guard-flowchart.png)

## Key Features
- Explainable Topic Clustering: Automatically extracts meaningful tokens and bigrams to detect recurring discussion subjects on post submission without black-box magic.
- Unified Post Menu Popout: Open Archive-Guard on any post to designate canonical guides, view topic history, or exempt false positives.
- Mod-Safe by Design: Operates purely as a moderator assistant with private mod reports and internal logs. No automatic post removals or intrusive user interruptions in v1.
- On-Demand Community Digests: Generate clean markdown summaries spotlighting your most frequently discussed topics and essential resources.
- Atomic Redis Reliability: Powered by Redis transactions and strict single-trigger idempotency for exact-once execution.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- Archive-Guard: Manage topic canonicals, recurring history, and ignore exemptions (Location: post)
- Archive-Guard: Generate Digest: Compile and preview the latest recurring topic digest (Location: subreddit)

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- enableModReports: Enable Mod Reports for Recurring Topics (boolean, default: true). When enabled, Archive-Guard submits a private mod report when a recurring topic is detected.
- minOverlapScore: Minimum Match Confidence Threshold (%) (number, default: 65). Conservative baseline is 65%. Increase to reduce flags; decrease to catch broader variations.

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
- Hashes (structured records & alias indices)
- Sorted Sets (time-series audit logs)

## Setup and Usage
- Install: Add app via Reddit App Directory.
- Configure: Open Mod Tools -> App Settings in your subreddit to configure options.
- Launch: Use mod menu or triggers as configured.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.5 — 2026-09-05
- Standard fleet synchronization and maintenance.

0.0.4 — 2026-09-02
- Standard fleet synchronization and maintenance.

0.0.3 — 2026-08-30
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/archive-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/archive-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/archive-guard)
- [Support](https://www.reddit.com/r/grantdb)