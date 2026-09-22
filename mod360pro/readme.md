> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/mod360pro)

# Mod360 Pro

> **The ultimate 360-degree Reddit moderation powerhouse consolidating 14+ moderation tools into a single, lightning-fast waterfall engine.**

Mod360 Pro unifies keyword filters, domain policies, rate limits, duplicate detection, user eligibility gates, auto-flairing, and AI spam inspection into a coordinated, atomic moderation pipeline. Eliminate container duplication, end multi-bot sticky comment spam, and control your entire community protection from a sleek glassmorphic dashboard.

### ⚡ Key Highlights
- **Atomic Two-Phase Waterfall Engine**: Sub-50ms pre-AutoMod Redis fast-path (`onPostSubmit`) for spam floods, followed by deep multi-module content evaluation (`onPostCreate`).
- **Single Consolidated Moderation Notice**: No more competing bot comments. Violations across all modules accumulate into exactly one structured, professional notice.
- **Mutual-Exclusion Atomic Verdict Lock**: `SET NX` concurrency locks eliminate double-removal race conditions and container collisions across all trigger events.
- **Zero-Risk Shadow Testing Mode**: Safely run Mod360 Pro in background shadow mode with automated divergence tracking before switching to live enforcement.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/mod360pro-flowchart.png)

### The 5-Step Lifecycle

1. **Pre-Filter (onPostSubmit)**: New submissions hit fast Redis-only gates (< 50ms) to check suspended authors, sliding-window rate limits, duplicate hash fingerprints, and karma/age eligibility.
2. **Deep Content Evaluation (onPostCreate)**: Surviving posts undergo modular inspection for domain allow/blocklists, prohibited keywords, title formatting, and composite rules.
3. **Asynchronous AI Inspection**: Content requiring deep semantic analysis is scheduled with zero delay for background Gemini evaluation without blocking the trigger handler.
4. **Atomic Verdict & Single Sticky Notice**: When violations occur, Mod360 Pro locks the verdict atomically and formats a single, clean markdown notice with clear community guidelines.
5. **Auto-Flair & Mod Actions**: Clean submissions receive automated flair matching, while removed content is automatically locked and logged to the unified audit trail.

---

## Quick Setup (60-Second Onboarding)

1. **Install**: Add **Mod360 Pro** to your community via the Reddit App Directory.
2. **Open Dashboard**: Click **GuardHub: Mod360 Pro Dashboard** in Subreddit Mod Tools.
3. **Review Shadow Mode**: Review the pre-configured rules in Shadow Mode to verify accuracy against live community traffic.
4. **Activate Live Enforcement**: Once verified, toggle the operational mode to **Live Enforcement** in the Overview tab.

*All settings, rules, and audit logs are managed directly within your native dashboard.*

---

## Core Features

- **Unified Frequency Limiter**: Sliding-window rate limiter preventing submission floods, burst spam, and rapid-fire cross-posting.
- **Domain & Shortener Guard**: Built-in protection against link shorteners, affiliate redirects, and unapproved external domains.
- **Regex & Keyword Engine**: Multi-pattern keyword groups with word-boundary matching, case-sensitivity controls, and instant test simulation.
- **Automated Shadow Parity Queue**: Automatically logs discrepancies between legacy moderation actions and Mod360 Pro predictions for zero-risk migration.
- **Fleet Standard Responsive Dashboard**: Native, inline webview control center with smooth 48px stepped tab scrolling and mobile auto-zoom protection.

---

## The Old Way vs. The Mod360 Pro Way

| Traditional Micro-App Setup | With Mod360 Pro |
| :--- | :--- |
| 10–15 separate apps spinning up redundant containers per post | **Single container, unified pipeline** with 93% less resource overhead |
| 2–3 different bots posting competing sticky comments on removed posts | **Exactly one consolidated notice** detailing all rule violations clearly |
| Multiple fragmented settings panels across a dozen different apps | **One centralized glassmorphic control center** with 7 organized tabs |
| Untraceable race conditions and double-removals in mod log | **Atomic `SET NX` locks** guaranteeing deterministic, single-owner execution |

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

<sub>Built with ❤️ by GrantDB for the Reddit Developer Platform</sub>

---
*Built for Reddit's moderator community.*
