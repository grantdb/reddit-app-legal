> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/mod360pro)

# Mod360 Pro

> **The ultimate 360-degree Reddit moderation control center delivering an enterprise-grade, lightning-fast waterfall evaluation engine.**

Mod360 Pro unifies keyword filters, domain policies, sliding-window rate limits, duplicate detection, user eligibility gates, timed quarantine state machines, canonical guide suggestions, false-positive rescue triage, two-way wiki sync, and disaster recovery snapshots into a single atomic moderation pipeline. End fragmented moderation scripts, eliminate competing bot sticky comments, and govern community safety from an intuitive, high-contrast dashboard.

### ⚡ Key Highlights
- **Atomic Two-Phase Waterfall Engine**: Sub-10ms pre-AutoMod Redis fast-path (`onPostSubmit`) for spam floods, followed by deep multi-module content evaluation (`onPostCreate`).
- **Timed Quarantine State Machine**: Filter blocked domains and unverified accounts into a timed quarantine with configurable auto-removal countdowns and 1-click mod release.
- **Single Consolidated Moderation Notice**: No more competing bot comments. Violations across all modules accumulate into exactly one structured, professional notice.
- **Modular Safety Architecture**: Native modules for account status filtering, flair & email verification tiers, canonical wiki guide suggestions, 0–100 safety score calculation, false-positive rescue triage, two-way wiki sync, and modmail disaster recovery snapshots.
- **In-Feed Mod Quick Actions**: Instant context menu tools (`Check Reputation`, `Quick Approve`, `Quick Remove`, and `Export Backup to Modmail`) directly on community posts and comments.
- **Mutual-Exclusion Atomic Verdict Lock**: `SET NX` concurrency locks eliminate double-removal race conditions and container collisions across all trigger events.
- **Zero-Risk Shadow Testing Mode**: Safely run Mod360 Pro in background shadow mode with automated divergence tracking before switching to live enforcement.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/mod360pro-flowchart.png)

### The 6-Step Lifecycle

1. **Pre-Filter (onPostSubmit)**: New submissions hit fast Redis-only gates (< 10ms) to check suspended/shadowbanned authors, sliding-window rate limits, duplicate hash fingerprints, and verification gates.
2. **Deep Content Evaluation (onPostCreate)**: Surviving posts undergo modular inspection for domain allow/blocklists, prohibited keywords, title formatting, and composite rules.
3. **Timed Quarantine Triage**: Configurable rules route suspicious links or edge-case users into a temporary quarantine state with automated expiration timers.
4. **Canonical Guide Suggestions**: Clean, non-violating submissions are evaluated against community topic keywords to suggest authoritative guides.
5. **Atomic Verdict & Single Sticky Notice**: When violations occur, Mod360 Pro locks the verdict atomically, logs candidate details for false-positive rescue, and formats a single clean markdown notice.
6. **Auto-Flair & Mod Actions**: Clean submissions receive automated flair matching, while removed content is automatically locked and logged to the unified audit trail.

---

## Quick Setup (60-Second Onboarding)

1. **Install**: Add **Mod360 Pro** to your community via the Reddit App Directory.
2. **Open Dashboard**: Click **Mod360 Pro Dashboard** in Subreddit Mod Tools.
3. **Review Shadow Mode**: Review the pre-configured rules in Shadow Mode to verify accuracy against live community traffic.
4. **Activate Live Enforcement**: Once verified, toggle the operational mode to **Live Enforcement** in the Overview tab.

*All settings, rules, wiki sync, and audit logs are managed directly within your native dashboard.*

---

## Core Capabilities & Key Features

- **Suspended Account Pre-Filter**: Sub-10ms fast gate rejecting suspended, shadowbanned, or deleted accounts before other checks run.
- **Timed Quarantine State Machine**: Configure blocked domains and suspended accounts to filter into temporary quarantine for a set duration (15m, 30m, 1h, 2h, 4h, 8h, 24h, 48h) before permanent removal.
- **Verification Tiers & Email Gates**: Require approved author flair templates, flair badges, or verified Reddit email addresses.
- **Canonical Guide Suggestions**: Automatically match submissions against community guide topics and post helpful guide links on clean posts.
- **Reputation Safety Score & Mod Menu Actions**: 0–100 reputation score calculated from account age, karma, and status with in-feed menu actions (`Check Reputation`, `Quick Approve`, `Quick Remove`).
- **False-Positive Rescue Hub**: Triage hub in dashboard capturing edge-case removals for instant 1-click restoration.
- **Two-Way Wiki Policy Sync**: Synchronize active content rules, domain policies, and user gates directly to and from `r/subreddit/wiki/mod360_rules`.
- **Disaster Recovery Backup**: 1-click snapshot dispatching the entire encrypted configuration to mod team modmail for permanent backup.
- **Sliding-Window Frequency Limiter**: Redis sliding-window counters preventing burst spam, rapid submissions, and cross-posting floods.
- **Domain & Shortener Guard**: Built-in blocklists for URL shorteners, chat invites, tracking parameters, and unapproved domains.
- **Regex & Keyword Engine**: Multi-pattern keyword groups with word-boundary matching, case-sensitivity controls, and instant test simulation.
- **High-Contrast Responsive Dashboard**: Native webview control center with theme switching, fullscreen mode, 48px stepped tab navigation, zero raw emojis, and mobile auto-zoom protection.

---

## The Old Way vs. The Mod360 Pro Way

| Traditional Setup | With Mod360 Pro |
| :--- | :--- |
| Disconnected scripts spinning up redundant execution per post | **Single container, unified pipeline** with minimal resource overhead |
| 2–3 different bots posting competing sticky comments on removed posts | **Exactly one consolidated notice** detailing all rule violations clearly |
| Multiple fragmented settings panels scattered across Reddit | **One centralized high-contrast control center** with 11 organized tabs |
| Immediate binary removal with no second chance for marginal posts | **Timed Quarantine State Machine** with automated countdown timers |
| Manual, untraceable false-positive recoveries across separate queues | **Integrated Rescue Hub & 0–100 Reputation Safety Score** |
| Fragile local settings lost on app uninstall or reinstall | **Automated Two-Way Wiki Sync & Modmail Disaster Backups** |

---

## Designed to Assist Moderators / Privacy & Ethics

Mod360 Pro is engineered with human-in-the-loop principles. All automated actions are transparent, auditable, and subject to moderator override. The app logs zero personal data (PII), strictly respecting Reddit's privacy rules and developer standards.

---

## Support

Need assistance or want to suggest a feature?
- Visit our support hub at [r/grantdb](https://www.reddit.com/r/grantdb)
- Reach out via Reddit Modmail for assistance.

---

## Legal

- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/mod360pro/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/mod360pro/PRIVACY.md)

---
*Built for Reddit's moderator community.*
