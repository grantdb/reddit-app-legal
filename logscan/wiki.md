> [Full User Guide](https://www.reddit.com/r/grantdb/wiki/logscan/) | **Technical Reference & Settings Spec**

# Logscan

Category: Observability  
Version: v0.0.6  
Visibility: Unlisted  
Summary: Structured, cross-subreddit operational log buffering, redaction, and scheduled telemetry reporting to a central Logscan collector.

## Overview
Structured, cross-subreddit operational log buffering, redaction, and scheduled telemetry reporting to a central Logscan collector.

## Key Features
- Not documented yet.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)
- http: External HTTP Fetch access [Domains: zboivpuygpsapoejfbpf.supabase.co]

## Triggers and Activation
### Menu Actions
- Logscan: Run Diagnostic Sample Events: Moderator menu action (Location: subreddit)
- Logscan: Flush Queue Now: Moderator menu action (Location: subreddit)

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- LOGSCAN_SETTING_KEYS.ENDPOINT: Logscan Collector Endpoint URL (string, default: -). HTTPS base URL for the central Logscan collector. Hostname must match devvit.json permissions.http.domains.
- LOGSCAN_SETTING_KEYS.API_KEY: Logscan Ingest API Key (string, default: -). Bearer ingest API key managed by the app developer via Devvit CLI.
- LOGSCAN_SETTING_KEYS.ENABLED: Enable Logscan Structured Reporting (boolean, default: true). Buffer redacted operational logs in Redis and flush to the Logscan collector.
- LOGSCAN_SETTING_KEYS.MIN_LEVEL: Logscan Minimum Log Level (select, default: info). Logscan Minimum Log Level
- LOGSCAN_SETTING_KEYS.SAMPLE_RATE_INFO: Logscan Info Sample Rate (0 to 1) (number, default: 1). Logscan Info Sample Rate (0 to 1)
- LOGSCAN_SETTING_KEYS.SAMPLE_RATE_DEBUG: Logscan Debug Sample Rate (0 to 1) (number, default: 0.1). Logscan Debug Sample Rate (0 to 1)

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
- Key patterns: logscan:scheduler:job_ids, logscan:rollup:error_count, logscan:queue:v1, node:fs, node:path

## Setup and Usage
- Update `permissions.http.domains` in `apps/logscan/devvit.json` to your exact Logscan collector hostname (no wildcards, protocols, or paths).
- Configure the developer-managed App-scoped settings (`logscan_endpoint` and secret `logscan_api_key`) via the Devvit CLI.
- Install the app on a test subreddit and run the moderator menu item Logscan: Run Diagnostic Sample Events to verify end-to-end delivery.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.6 — 2026-11-24
- Fix 404 Terms of Service and Privacy Policy links in README.md to point to reddit-app-legal GitHub URLs

0.0.4 — 2026-11-24
- Standard fleet synchronization and maintenance.

0.0.3 — 2026-11-22
- Initial Logscan reference Devvit app demonstrating @devvit-fleet/logscan-sdk integration, Redis buffering, and scheduled flushing

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/logscan/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/logscan/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/logscan)
- [Support](https://www.reddit.com/r/grantdb)