> **User Guide & Overview** | [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/piracy-guard)

# Piracy Guard

> **Configurable piracy-content moderation filters for Reddit communities.**

Piracy Guard helps moderators review potentially piracy-related posts and comments using deterministic keyword, phrase, regex, and URL-based filters. Designed for human-review safety, it flags likely violations for moderator determination without automatically deleting content, banning users, or messaging authors.

## At a Glance

- **Webview Control Center**: Manage enforcement mode (`Report Only`, `Filter to Mod Queue`, `Log Only`), minimum confidence, scan scope, allowlists, category/rule overrides, custom rules, and a dry-run Test Console directly inside Reddit.
- **18 Deterministic Presets**: Covers Software, Games, Streaming & Media, Ebooks & Courses, Accounts & Credentials, and Requests & Sourcing with ReDoS-protected custom rule support.
- **Operational Safeguards**: Built-in Safe Mode (Testing / Dry Run), Panic Disable, automatic Circuit Breaker on API failures, optimistic concurrency (`baseVersion`), and 20-revision rollback history.
- **Review-First & Zero PII**: Never auto-removes content, bans users, or sends DMs/modmail. Telemetry stores zero usernames or post bodies and expires automatically after 30 days.

## How It Works: The 4-Step Operational Pipeline

### 01 · Ingest New Submissions

> **Non-blocking post and comment evaluation with 24-hour idempotency**
> - Newly submitted posts (`onPostSubmit`) and comments (`onCommentSubmit`) are evaluated asynchronously with Redis idempotency locking to prevent duplicate actions.
> - Allowlisted domains, allowlisted users, and disabled scan scopes (titles, bodies, URLs) are respected before rules run.

---

### 02 · Evaluate Presets & Custom Rules

> **Normalized matching across 6 piracy categories and moderator custom rules**
> - Text and URLs are normalized and checked against 18 built-in presets plus up to 50 subreddit-specific custom keyword, phrase, regex, or domain rules.
> - Each match is scored by confidence (`low`, `medium`, `high`) and compared against your configured minimum confidence threshold.

---

### 03 · Enforce With Operational Safeguards

> **Human-review actions protected by Safe Mode, Panic Disable, and Circuit Breaker**
> - Matching items are reported to the mod queue (`report_only`), filtered with `keep: true` (`filter_to_queue`), or logged (`log_only`) based on your Control Center configuration.
> - Low-confidence matches, Safe Mode (Dry Run), and tripped Circuit Breaker states clamp actions to log-only without mutating Reddit content.

---

### 04 · Inspect, Tune & Roll Back

> **Live rule health metrics, false-positive feedback, and versioned recovery**
> - Moderators can inspect matched rules via post/comment menu actions (`Piracy Guard: Rule details`) and log deduplicated false positives (`Piracy Guard: Mark false positive`).
> - Review 24h/7d/30d telemetry, export/import JSON configs with diff previews, and restore any of the last 20 configuration revisions.

## Quick Setup

1. **Install**: Add **Piracy Guard** to your subreddit from the Reddit App Directory.
2. **Open Control Center**: Launch **Piracy Guard: Dashboard** from your subreddit moderation menu.
3. **Configure & Test**: Set your Enforcement Mode, Minimum Confidence, and categories in the **Configuration** and **Preset Rules** tabs, then verify behavior with the **Test Console**.

---

## Support

> **Community Support & Feature Requests**
> For questions, troubleshooting, or bug reports, join the official community:
> **[https://www.reddit.com/r/grantdb](https://www.reddit.com/r/grantdb)**

- **User Guide**: [https://www.reddit.com/r/grantdb/wiki/piracy-guard/](https://www.reddit.com/r/grantdb/wiki/piracy-guard/)
- **Technical Reference**: [https://www.reddit.com/r/grantdb/wiki/index/all-apps/piracy-guard/](https://www.reddit.com/r/grantdb/wiki/index/all-apps/piracy-guard/)

---

## Legal

- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/piracy-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/piracy-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
