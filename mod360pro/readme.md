> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/mod360pro)

# Mod360 Pro

> **The ultimate 360-degree Reddit moderation powerhouse consolidating 14+ moderation tools — including suspended-remove, verify-guard, archive-guard, queue-guard, rescue-guard, wiki-guard, and mod-snapshot — into a single, lightning-fast waterfall engine.**

Mod360 Pro unifies keyword filters, domain policies, rate limits, duplicate detection, user eligibility & verification gates, canonical guide clustering, false-positive rescue triage, two-way wiki sync, and disaster recovery snapshots into a coordinated, atomic moderation pipeline. Eliminate container duplication, end multi-bot sticky comment spam, and control your entire community protection from a sleek glassmorphic dashboard.

### ⚡ Key Highlights
- **Atomic Two-Phase Waterfall Engine**: Sub-10ms pre-AutoMod Redis fast-path (`onPostSubmit`) for spam floods, followed by deep multi-module content evaluation (`onPostCreate`).
- **Single Consolidated Moderation Notice**: No more competing bot comments. Violations across all modules accumulate into exactly one structured, professional notice.
- **7 Consolidated Moderation Powerhouses**: Built-in gates for suspended account pre-filtering, flair & email verification tiers, canonical wiki guide suggestions, 0–100 safety score calculation, false-positive rescue triage, two-way wiki sync, and modmail disaster recovery snapshots.
- **In-Feed Mod Quick Actions**: Instant context menu tools (`Check Reputation`, `Quick Approve`, `Quick Remove`, and `Export Backup to Modmail`) directly on community posts and comments.
- **Mutual-Exclusion Atomic Verdict Lock**: `SET NX` concurrency locks eliminate double-removal race conditions and container collisions across all trigger events.
- **Zero-Risk Shadow Testing Mode**: Safely run Mod360 Pro in background shadow mode with automated divergence tracking before switching to live enforcement.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/mod360pro-flowchart.png)

### The 5-Step Lifecycle

1. **Pre-Filter (onPostSubmit)**: New submissions hit fast Redis-only gates (< 10ms) to check suspended/shadowbanned authors (`suspended-remove`), sliding-window rate limits, duplicate hash fingerprints, and verification gates (`verify-guard`).
2. **Deep Content Evaluation (onPostCreate)**: Surviving posts undergo modular inspection for domain allow/blocklists, prohibited keywords, title formatting, and composite rules.
3. **Canonical Guide Suggestions**: Clean, non-violating submissions are evaluated against community topic keywords to suggest authoritative guides (`archive-guard`).
4. **Atomic Verdict & Single Sticky Notice**: When violations occur, Mod360 Pro locks the verdict atomically, logs candidate details for false-positive rescue (`rescue-guard`), and formats a single clean markdown notice.
5. **Auto-Flair & Mod Actions**: Clean submissions receive automated flair matching, while removed content is automatically locked and logged to the unified audit trail.

---

## Quick Setup (60-Second Onboarding)

1. **Install**: Add **Mod360 Pro** to your community via the Reddit App Directory.
2. **Open Dashboard**: Click **GuardHub: Mod360 Pro Dashboard** in Subreddit Mod Tools.
3. **Review Shadow Mode**: Review the pre-configured rules in Shadow Mode to verify accuracy against live community traffic.
4. **Activate Live Enforcement**: Once verified, toggle the operational mode to **Live Enforcement** in the Overview tab.

*All settings, rules, wiki sync, and audit logs are managed directly within your native dashboard.*

---

## Core Capabilities & Consolidated Powerhouses

- **Suspended Account Pre-Filter (`suspended-remove`)**: Sub-10ms fast gate rejecting suspended, shadowbanned, or deleted accounts before other checks run.
- **Verification Tiers & Email Gates (`verify-guard`)**: Require approved author flair templates, flair badges, or verified Reddit email addresses.
- **Canonical Guide Suggestions (`archive-guard`)**: Automatically match submissions against community guide topics and post helpful guide links on clean posts.
- **Reputation Safety Score & Mod Menu Actions (`queue-guard`)**: 0–100 reputation score calculated from account age, karma, and status with in-feed menu actions (`Check Reputation`, `Quick Approve`, `Quick Remove`).
- **False-Positive Rescue Hub (`rescue-guard`)**: Triage hub in dashboard capturing edge-case removals for instant 1-click restoration.
- **Two-Way Wiki Policy Sync (`wiki-guard`)**: Synchronize active content rules, domain policies, and user gates directly to and from `r/subreddit/wiki/mod360_rules`.
- **Disaster Recovery Backup (`mod-snapshot`)**: 1-click snapshot dispatching the entire encrypted configuration to mod team modmail for permanent backup.
- **Sliding-Window Frequency Limiter**: Redis sliding-window counters preventing burst spam, rapid submissions, and cross-posting floods.
- **Domain & Shortener Guard**: Built-in blocklists for URL shorteners, chat invites, tracking parameters, and unapproved domains.
- **Regex & Keyword Engine**: Multi-pattern keyword groups with word-boundary matching, case-sensitivity controls, and instant test simulation.
- **Fleet Standard Responsive Dashboard**: Native webview control center with theme switching (☀️/🌙), fullscreen mode (⛶/🗗), 48px stepped tab navigation, and mobile auto-zoom protection.

---

## The Old Way vs. The Mod360 Pro Way

| Traditional Micro-App Setup | With Mod360 Pro |
| :--- | :--- |
| 10–15 separate apps spinning up redundant containers per post | **Single container, unified pipeline** with 93% less resource overhead |
| 2–3 different bots posting competing sticky comments on removed posts | **Exactly one consolidated notice** detailing all rule violations clearly |
| Multiple fragmented settings panels across a dozen different apps | **One centralized glassmorphic control center** with 10 organized tabs |
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
