> **User Guide & Overview** | [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/logscan)

# Logscan

> **Reference Devvit app demonstrating redacted, Redis-buffered operational logging to a central Logscan collector.**

Logscan shows how monitored Devvit apps integrate `@devvit-fleet/logscan-sdk` to report structured errors, scheduler lifecycle events, and operational warnings across subreddit installations without violating Devvit's per-installation Redis isolation. Logscan complements, and does not replace, `npm run logs`, which remains necessary for uninstrumented crashes, OOMs, and platform-level failures.

## At a Glance

- Buffers redacted operational logs in per-installation Devvit Redis using priority-aware capped sorted sets.
- Drains queued events to the central Logscan collector via a 1-minute Devvit Scheduler job (`logscan_flush`), staying within Devvit's 10-job limit (3 recurring jobs total).
- Protects collector credentials in developer-managed App-scoped settings (`logscan_endpoint`, `logscan_api_key`).
- Demonstrates realistic logging for `AppInstall`, `AppUpgrade`, scheduler jobs, Reddit API failures, Redis timeouts, webhook errors, and moderator actions.

## How It Works: The 3-Step Operational Pipeline

### 01 · Redact and Buffer Locally

> **Per-installation Redis isolation with client-side allowlisting**
> - Every handler creates a request-scoped logger bound to a correlation ID (no `AsyncLocalStorage` or `setInterval`).
> - Context keys are filtered through an explicit allowlist, sensitive strings are redacted, and stacks are capped at 20 lines before enqueueing into installation Redis.
> - On queue overflow, the oldest low-severity events are evicted first so `error` and `fatal` events are preserved.

---

### 02 · Scheduled Batch Delivery

> **Bounded cron jobs flush batches over HTTPS**
> - `logscan_flush` runs every 1 minute to drain up to 50 queued events and POST them to `POST /v1/events/batch`.
> - If delivery fails, events remain in Redis for the next scheduled tick. If Redis itself fails during logging, the SDK attempts at most one direct 2.5-second fallback POST without retries or recursion.

---

### 03 · Cross-Subreddit Incident Reporting

> **Centralized grouping and AI-ready reports**
> - The external `services/logscan-collector` service aggregates matching `(signature, app)` errors across subreddits into prioritized incidents.
> - Operators and AI agents query `GET /v1/report`, `GET /v1/compare`, and `GET /v1/incidents/:id/*` while keeping `npm run logs` available for uninstrumented platform crashes.

## Quick Setup

1. Update `permissions.http.domains` in `apps/logscan/devvit.json` to your exact Logscan collector hostname (no wildcards, protocols, or paths).
2. Configure the developer-managed App-scoped settings (`logscan_endpoint` and secret `logscan_api_key`) via the Devvit CLI.
3. Install the app on a test subreddit and run the moderator menu item **Logscan: Run Diagnostic Sample Events** to verify end-to-end delivery.

## Integration and Playtest Checklist

Use this checklist to verify `apps/logscan` end-to-end before onboarding additional fleet apps:

1. **Configure Collector Endpoint and API Key**:
   - Confirm `permissions.http.domains` in `apps/logscan/devvit.json` contains `zboivpuygpsapoejfbpf.supabase.co` (exact hostname; no wildcards, protocols, or paths). `zboivpuygpsapoejfbpf.supabase.co` must have confirmed Reddit HTTP Fetch domain approval before live delivery can be considered verified.
   - Set App-scoped settings via Devvit CLI (`logscan_endpoint` = `https://zboivpuygpsapoejfbpf.supabase.co/functions/v1/logscan-ingest`, `logscan_api_key` = your dedicated `LOGSCAN_INGEST_API_KEY`).
   - Confirm subreddit moderators cannot see `logscan_endpoint` or `logscan_api_key` in subreddit installation settings.
2. **Verify Events Reach the Collector**:
   - Start `apps/logscan` with `devvit playtest` on a test subreddit.
   - Run **Logscan: Run Diagnostic Sample Events** from the subreddit moderator menu.
   - Wait 1 minute for `logscan_flush` and query `GET /v1/report?since=15m` with `LOGSCAN_READ_API_KEY`.
3. **Verify Webhook Failure Logging**:
   - Confirm the `webhook.delivery_failed` (`HTTP_502`) event appears in `GET /v1/incidents` with component `webhook` and redacted context.
4. **Verify Redis Failure Logging & Fallback**:
   - Confirm `redis.operation_failed` (`REDIS_TIMEOUT`) appears in the report.
   - Verify via SDK unit tests (`npm test --workspace=@devvit-fleet/logscan-sdk`) that a real Redis outage triggers at most one direct 2.5s HTTPS fallback POST with zero retries.
5. **Verify Reddit API Failure Logging**:
   - Confirm `reddit.api_request_failed` (`HTTP_429`) appears in the report with `retryAfterSec` preserved in allowlisted context.
6. **Verify Cross-Subreddit Incident Aggregation**:
   - Install `apps/logscan` on two test subreddits (or run `npm run seed --workspace=@devvit-fleet/logscan-collector`) and trigger the diagnostic menu item in both.
   - Confirm `GET /v1/report` shows **one** incident with both subreddits listed in `subreddits` and accurate `perSubreddit` counts.
7. **Verify Duplicate Events Do Not Inflate Counts**:
   - Re-POST an already ingested batch to `POST /v1/events/batch` and confirm `deduplicated` matches the batch size while incident `count`, `firstSeen`, and `evidence` remain unchanged.
8. **Verify Logscan Failures Do Not Recurse**:
   - Temporarily configure an invalid `logscan_api_key` or stop the collector, trigger diagnostic events, and confirm `logscan_flush` leaves events in Redis, logs a single local warning, and never enqueues new Logscan failure events.

## Support

> **Official Support Community**: [https://www.reddit.com/r/grantdb](https://www.reddit.com/r/grantdb)
>
> - User Guide: [https://www.reddit.com/r/grantdb/wiki/logscan/](https://www.reddit.com/r/grantdb/wiki/logscan/)
> - Technical Reference: [https://www.reddit.com/r/grantdb/wiki/index/all-apps/logscan/](https://www.reddit.com/r/grantdb/wiki/index/all-apps/logscan/)

## Legal

- [Privacy Policy](PRIVACY.md)
- [Terms of Service](TERMS.md)

---
*Built for Reddit's moderator community.*
