# Privacy Policy for Logscan

Effective Date: November 22, 2026

## Operational Log Metadata Collected
This application collects structured operational telemetry to diagnose app failures across subreddit installations. Collected fields are strictly limited to:
- Application name, application version, subreddit name, and installation ID
- Event timestamp, severity level, component name, event name, error code, and correlation ID
- Allowlisted technical metadata (such as HTTP status codes, retry attempt counts, duration in milliseconds, and job names)
- Truncated stack traces (maximum 20 lines)

## External Transmission to the Logscan Collector
Redacted operational events are buffered in per-installation Devvit Redis and transmitted over HTTPS by a scheduled job to the developer-managed central Logscan collector declared in `devvit.json`.

## Redaction and Prohibited Data
Before events leave Reddit infrastructure, `@devvit-fleet/logscan-sdk` applies context-key allowlisting and strips sensitive values including OAuth tokens, API keys, passwords, authorization headers, email addresses, IP addresses, Reddit user IDs, private messages, and raw user-generated post or comment content.

## Retention Period
- Raw structured events are retained in the Logscan collector for up to 14 days by default (configurable via `LOGSCAN_EVENT_RETENTION_DAYS`).
- Aggregated incident summaries are retained for up to 90 days (configurable via `LOGSCAN_INCIDENT_RETENTION_DAYS`).

## How to Disable Reporting
Subreddit moderators may disable structured reporting at any time by setting **Enable Logscan Structured Reporting** (`logscan_enabled`) to `false` in the app's subreddit installation settings.

## Contact
Contact the developer via r/grantdb on Reddit for privacy inquiries or data deletion requests.
