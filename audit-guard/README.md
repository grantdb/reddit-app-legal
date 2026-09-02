> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/audit-guard)

# GuardHub: Audit Guard 🛡️

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Hardened-red?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Logging-8A2BE2?style=for-the-badge)

> **Maintain a transparent, searchable audit ledger of moderation actions and config changes.**

Audit Guard provides your moderation team with a central, chronological security ledger. Record and review moderation events and configuration changes across your subreddit through an interactive dashboard, giving you complete transparency into what actions were taken, by whom, and when.

---

## At a Glance

- **Centralized audit ledger**: Index moderation events across your community in chronological order.
- **Track configuration shifts**: Maintain a clear history of setting adjustments and policy changes.
- **Search and filter logs**: Quickly isolate events by moderator, action type, or target user in an interactive dashboard.
- **On-demand recording**: Record and log moderation actions directly from the dashboard interface.
- **Private dashboard access**: Review logs securely from an unlisted custom post inside your subreddit.

---

## The Old Way vs. The Audit Guard Way

| Traditional Workflow | With Audit Guard |
| :--- | :--- |
| Sifting through raw, cluttered Reddit mod log exports | **Searchable, filterable audit ledger** in a clean native dashboard |
| Losing track of who modified bot and filter settings | **Chronological change tracking** recording exact configuration adjustments |
| Disconnected logs scattered across separate external bots | **Unified event stream** consolidating automated and manual mod actions |
| Manually compiling compliance reports for senior mods | **Exportable event summaries** with full timestamp and author context |
| Mod team debating the timeline of a past moderation incident | **Deterministic timestamped records** preserving an immutable history |

---

## Built for Team Accountability & Oversight

- **Dashboard Event Recording**: Record moderation events, enforcement actions, and configuration updates directly from the interactive dashboard.
- **Historical Change Tracking**: Records a clean, accessible timeline of setting modifications so your team stays aligned on policy changes.
- **Fast In-Dashboard Search**: Filter events by moderator username, action category, or specific keywords to trace past incidents in seconds.
- **Automated Retention Management**: Maintains a rolling historical buffer in Redis with automatic deduplication and state hygiene.
- **Low-Friction Operation**: Log events from the dashboard without requiring manual log exports or external spreadsheet maintenance.
- **Dedicated Audit Center**: Access an interactive Webview dashboard from Subreddit Mod Tools to inspect logs and review activity trends.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/audit-guard-flowchart.png)

### Your Four-Step Workflow

1. **Record**: A moderator logs a moderation action or configuration change from the dashboard.
2. **Normalize**: Audit Guard normalizes the event payload with timestamps and metadata.
3. **Index**: Events are appended to a chronological Redis sorted-set ledger with deduplication safeguards.
4. **Inspect**: Moderators open the interactive dashboard to search, filter, and review historical audit records.

---

## Quick Setup

1. **Install**: Add **Audit Guard** to your subreddit through the Reddit App Directory.
2. **Initialize Dashboard**: Select **GuardHub: Create Audit Dashboard** from Subreddit Mod Tools.
3. **Record Events**: Use the dashboard to log moderation actions and configuration changes.
4. **Review**: Open your dashboard anytime to inspect event history and search specific actions.

*No external database setup required. Complete moderation transparency directly in your subreddit.*

---

## Advanced Capabilities

Audit Guard is engineered for high-integrity event ingestion and efficient timeline querying.

- **Chronological Redis Ledger**: Stores events in a Redis Sorted Set (`ZSET`) indexed by millisecond epoch timestamps.
- **Idempotent Ingestion Engine**: Uses transactional state tracking to prevent duplicate log entries during retries.
- **Interactive React Webview**: Provides client-side search, filtering by action type, and real-time pagination.
- **Rolling Buffer Capping**: Automatically trims historical logs to maintain optimal performance and storage limits.

---

## Designed to Assist Moderators

Audit Guard maintains chronological logs of actions and events to assist team oversight and community transparency. Audit records serve as historical reference material—human moderators retain full authority over moderation policies, disciplinary decisions, and community guidelines.

---

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

---

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/audit-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/audit-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
