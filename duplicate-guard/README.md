> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/duplicate-guard)

# GuardHub: Duplicate Guard 🛡️

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Hardened-red?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blueviolet?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Spam_Control-8A2BE2?style=for-the-badge)

> **Catch repost bots, filter duplicate topics, and keep your community feed fresh.**

Duplicate Guard stops repetitive topics, reworded reposts, and content floods before they reach your front page. Comparing incoming submission titles against recent community posts using configurable similarity algorithms, it filters duplicates automatically without manual mod queue searching.

---

## At a Glance

- **Stop repetitive topics**: Catch duplicate submissions covering the exact same subject.
- **Configurable match modes**: Choose between strict exact titles or flexible similarity algorithms.
- **Adjustable lookback window**: Control how many recent posts or days to evaluate for duplicates.
- **Custom moderation actions**: Automatically filter to queue, report, remove, or leave an explanatory comment.
- **Granular exemptions**: Protect megathreads, moderator posts, and specific flairs from duplicate checks.

---

## The Old Way vs. The Duplicate Guard Way

| Traditional Workflow | With Duplicate Guard |
| :--- | :--- |
| Manually searching subreddit archives to find original posts | **Automated similarity matching** against recent community submissions |
| Mod queue flooded with identical breaking-news submissions | **Instant duplicate filtering** as soon as posts are submitted |
| Manually commenting on reposts to explain why they were removed | **Automated removal notices** linking users to the active discussion |
| Accidental double-actions caused by duplicate platform events | **Effectively-once execution locks** guaranteeing single mod actions |
| Manually exempting recurring daily megathreads | **Built-in flair and title exemptions** bypassing checks automatically |

---

## Built for High-Quality Feeds

- **Multiple Match Modes**: Select from Strict (exact normalized match), Balanced, or Aggressive similarity matching.
- **Configurable Lookback Windows**: Set lookback horizons from 25 to 500 recent submissions to match your community's posting volume.
- **Flexible Action Pipelines**: Choose to silently filter for review, flag with reports, or remove immediately with an automated sticky comment.
- **Comprehensive Exemptions**: Easily exempt moderators, approved users, designated post flairs, or specific regex title patterns.
- **Deduplication Safeguards**: Built-in atomic locking prevents duplicate actions during Reddit event retries.
- **Seamless Settings Management**: Configure all threshold settings directly from your native Subreddit Mod Tools.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/duplicate-guard-flowchart.png)

### Your Four-Step Workflow

1. **Receive**: Duplicate Guard receives new submission events via `PostSubmit` and `PostCreate` triggers.
2. **Verify**: The author, post flair, and title are verified against configured exemption rules.
3. **Compare**: The submission title is compared against recent community posts in the lookback cache.
4. **Enforce**: When a duplicate match is detected, the configured action (e.g. `Filter`, `Remove`, or `Comment & Remove`) executes.

---

## Quick Setup

1. **Install**: Add **Duplicate Guard** to your subreddit through the Reddit App Directory.
2. **Configure**: Open **Mod Tools > App Settings > Duplicate Guard**.
3. **Set Thresholds**: Choose your preferred Match Mode (Strict or Balanced) and lookback post limit.
4. **Save**: Settings apply immediately to all incoming community submissions.

*No external tools required. Automated duplicate protection right inside Reddit.*

---

## Advanced Capabilities

Duplicate Guard is engineered for fast token comparison and reliable event processing across active subreddits.

- **Token Similarity Engine**: Uses tokenized text normalization (lowercasing, punctuation stripping, stopword filtering) and Jaccard similarity scoring.
- **Redis Lookback Index**: Maintains a rolling sorted-set cache of recent submission titles with automatic TTL expiry.
- **Effectively-Once Guarantees**: Employs atomic Redis set locks to prevent duplicate execution across overlapping platform trigger deliveries.
- **Custom Comment Templates**: Supports customizable markdown removal comments with dynamic placeholders for original post links.

---

## Designed to Assist Moderators

Duplicate Guard evaluates title similarity to highlight likely duplicate topics and reposts. Similarity scores serve as assistive indicators to help keep feeds organized—human moderators maintain full authority to approve filtered posts, adjust match sensitivity, and grant exemptions at any time.

---

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

---

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/duplicate-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/duplicate-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
