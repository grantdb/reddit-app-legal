> **User Guide & Overview** | [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/gimmecode-guard)

# GimmeCode Guard

> **Automated low-effort code-request detection and weighted scoring engine for developer communities.**

**GimmeCode Guard** evaluates incoming posts and comments in developer and programming subreddits to detect low-effort "give me the code" requests. It uses weighted pattern scoring, configurable exemptions for OPs, moderators, and approved users, and non-destructive moderation actions so communities stay focused on constructive help.

---

## At a Glance

- **Weighted Pattern Scoring**: Evaluates submissions and comments against configurable low-effort request signals before taking action.
- **Smart Exemptions**: Automatically exempts OPs on their own threads, moderators, and approved users (with Redis caching and transient-error retries).
- **Atomic Metrics & Cooldowns**: Tracks evaluations and enforcement actions with atomic Redis counters and per-user cooldowns.
- **Interactive Control Center**: Manage thresholds, exemptions, and live stats from a clean custom-post moderator dashboard.

---

## How It Works: The 4-Step Operational Pipeline

### 01 · Event Ingestion

> **Post & Comment Trigger Capture**
> - Listens for new posts and comments in the subreddit.
> - Skips deleted authors and checks exemption rules for OPs, moderators, and approved users.

---

### 02 · Weighted Scoring

> **Pattern & Context Evaluation**
> - Runs the content through the `ScoringEngine` to measure low-effort code-request signals.
> - Compares the resulting score against the configured enforcement threshold (with `0` disabling enforcement).

---

### 03 · Cooldown & Action Gate

> **Controlled Moderation Response**
> - Enforces configured moderation actions (remove, filter, or report) when a submission exceeds the threshold.
> - Applies Tier 1 per-user cooldowns to prevent duplicate notifications or repeated actions.

---

### 04 · Telemetry & Dashboard

> **Atomic Stats & Moderator Review**
> - Increments atomic Redis counters for evaluated and actioned items.
> - Surfaces live metrics and configuration controls inside the subreddit's GimmeCode Guard dashboard.

---

## Quick Setup

1. **Install**: Add **GimmeCode Guard** to your subreddit via the Reddit App Directory.
2. **Configure Thresholds**: Open **Mod Tools > App Settings > GimmeCode Guard** (or the Control Center) to tune scoring thresholds, exemptions, and cooldowns.
3. **Verify**: Monitor initial evaluations in the dashboard and adjust thresholds to fit your community's norms.

---

## Support

> **Official Support Community**
> - Post questions, bug reports, or feature requests in [https://www.reddit.com/r/grantdb](https://www.reddit.com/r/grantdb).
> - Include the app name, what you expected, what happened, and any error text or screenshots.
> - [Full User Guide](https://www.reddit.com/r/grantdb/wiki/gimmecode-guard/)
> - [Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/gimmecode-guard/)

---

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/gimmecode-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/gimmecode-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
