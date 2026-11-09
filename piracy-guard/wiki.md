# Piracy Guard

Category: Moderation  
Version: v0.0.1  
Visibility: Unlisted  
Summary: Configurable piracy-content moderation filters for Reddit communities.

## Overview
Configurable piracy-content moderation filters for Reddit communities.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/piracy-guard-flowchart.png)

## Key Features
- Not documented yet.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- Piracy Guard: Mark false positive: Moderator menu action (Location: subreddit)
- Piracy Guard: Rule details: Moderator menu action (Location: subreddit)
- Piracy Guard: Test Console: Moderator menu action (Location: subreddit)
- Piracy Guard: Dashboard: Moderator menu action (Location: subreddit)

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- piracy_guard_enabled: Enable Piracy Guard (boolean, default: true). Enable Piracy Guard scanning for the subreddit.
- enforcement_mode: Enforcement Mode (select, default: report_only). What action Piracy Guard should take when a match meets the threshold.
- minimum_confidence: Minimum Confidence Threshold (select, default: medium). Minimum confidence required before reporting or filtering content.
- scan_posts: Scan Posts (boolean, default: true). Evaluate newly submitted posts.
- scan_comments: Scan Comments (boolean, default: true). Evaluate newly submitted comments.
- scan_titles: Scan Titles (boolean, default: true). Evaluate post titles against piracy rules.
- scan_bodies: Scan Bodies (boolean, default: true). Evaluate post and comment body markdown.
- scan_urls: Scan URLs (boolean, default: true). Extract and scan links against piracy domain patterns.
- allowlisted_domains: Allowlisted Domains (comma-separated) (string, default: ). Comma-separated domains (e.g. reddit.com, github.com) that should never trigger URL rules.
- allowlisted_subreddits: Allowlisted Subreddits (comma-separated) (string, default: ). Comma-separated subreddit names where Piracy Guard should remain inactive.
- allowlisted_users: Allowlisted Users (comma-separated) (string, default: ). Comma-separated usernames exempt from scanning.
- safe_mode: Safe Mode (Diagnostic & Telemetry Only) (boolean, default: false). Evaluates content and logs telemetry without taking filter or report actions.
- panic_disable: Panic Disable (Emergency Stop) (boolean, default: false). Immediately disables all scanning while preserving configuration and history.
- enable_evidence_snippets: Enable Evidence Snippets (boolean, default: false). Opt-in to storing sanitized 60-character evidence snippets in local telemetry.

## Automation Capabilities
- Submits Automated Comments: No — Does not submit automated comments.
- Attaches Removal Notes: No — Does not attach removal notes.
- Approves Content: Yes — Approves content.
- Removes or Filters Content: Yes — Removes or filters non-compliant submissions.
- Dispatches Modmail Alerts: No — Does not send modmail notifications.
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Hashes (structured records & alias indices)
- Key patterns: piracy-guard:circuit-breaker, piracy-guard:telemetry:totals, node:http, piracy-guard:config:current, piracy-guard:config:history, piracy-guard:config:lock

## Setup and Usage
- Install: Add app via Reddit App Directory.
- Configure: Open Mod Tools -> App Settings in your subreddit to configure options.
- Launch: Use mod menu or triggers as configured.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.1 — 2026-11-09
- Phase 4 production hardening: Circuit breaker (5-failure / 60s cooldown), Safe Mode (dry run clamping), Panic Disable emergency bypass, optimistic concurrency conflict detection (409 on baseVersion mismatch), FNV-1a configuration checksums, 30-day telemetry retention, token redaction in snippets, clear telemetry/history maintenance endpoints, and first-run onboarding checklist.
- All notable changes to the Piracy Guard application will be documented in this file.

0.1.0 — 2026-11-09
- Complete Devvit Web 5-tab moderator control center (Overview, Preset Rules, Custom Rules, Test Console, Configuration).
- deterministic preset filters across Software, Games, Streaming, Shadow Libraries, Credential Dumps, and Sourcing Requests.
- Self-healing circuit breaker pausing enforcement during platform outages (5 failures / 60-second cooldown).
- Safe Mode (dry run clamping to `log`) and Panic Disable emergency disengage.
- Optimistic Concurrency Control with HTTP 409 conflict detection for concurrent moderator edits.
- Deterministic 8-character FNV-1a configuration checksum generator.
- Duplicate-suppressed false-positive reporting and read-only rule violation details inspection.
- day retention on daily telemetry buckets with sensitive token and URL redaction.
- First-run interactive onboarding checklist.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/piracy-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/piracy-guard/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/piracy-guard)
- [Support](https://www.reddit.com/r/grantdb)