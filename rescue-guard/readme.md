> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/rescue-guard)

# GuardHub: RescueGuard 🛡️

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Hardened-red?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Discovery_Engine-8A2BE2?style=for-the-badge)

> **Surface overlooked submissions, empower manual moderator curation, and spotlight hidden gems across your subreddit.**

RescueGuard gives moderation teams an assistive, privacy-first discovery engine to find quality community submissions from the lookback window that slipped through the cracks with low engagement. Review a ranked queue of overlooked posts and manually spotlight worthy contributions with automated post flairs and distinguished sticky notices.

---

## At a Glance

- **Configurable Lookback Scan**: Analyzes recent subreddit submissions across customizable lookback windows (default: 30 days).
- **Engagement Velocity Ranking**: Prioritizes posts with low upvotes and low discussion counts using weighted scoring.
- **Minimum Age Filtration**: Prevents brand-new posts from surfacing before they have had natural feed exposure.
- **Single-Submission Gate**: Optionally excludes items or apps submitted multiple times across the lookback window.
- **Universal Deduplication Strategies**: Auto-detects app store package IDs, link domains, author identities, or normalized titles.
- **Moderator-in-the-Loop Review**: Zero automated highlights—human moderators maintain 100% final decision authority.
- **Multi-Action Spotlight**: Apply community spotlight post flairs, distinguished sticky comments, or feed pinning upon approval.
- **Direct-Key Redis Memory**: Retains audit and spotlight records to ensure reviewed items are never duplicated.

---

## The Old Way vs. The RescueGuard Way

| Traditional Workflow | With RescueGuard |
| :--- | :--- |
| Good posts getting lost in fast-moving subreddit feeds | **Automated low-attention discovery** surfacing overlooked content |
| Manually scrolling weeks of back-catalog looking for uncredited gems | **Ranked candidate review queue** delivered directly in Mod Tools |
| Accidental repeat reviews of previously dismissed posts | **Direct Redis audit memory** pruning reviewed posts automatically |
| Complicated external analytics scrapers and cron jobs | **Native Devvit architecture** operating securely inside Reddit |
| Unpredictable bot promotions of low-quality posts | **Human-moderator approval gate** ensuring only quality content is featured |

---

## Built for Community Post Discovery

- **Weighted Attention Scoring**: Ranks candidate submissions using `(score * 0.65) + (commentCount * 0.35)` with logarithmic age dampening.
- **Content Hygiene Safeguards**: Automatically filters out removed, spam, stickied, or deleted author posts.
- **Customizable Spotlight Flair**: Assign designated community showcase post flairs (e.g. `Community Spotlight`).
- **Distinguished Sticky Comments**: Post automated, transparent moderator comments highlighting the author and post.
- **Privacy-First Architecture**: Stores only post IDs and decision timestamps in Redis—zero post text or user PII is ever retained.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/rescue-guard-flowchart.png)

### Your Four-Step Workflow

1. **Trigger**: A moderator clicks **GuardHub: RescueGuard Review** in the subreddit menu.
2. **Scan & Rank**: RescueGuard scans submissions from the lookback window, excludes multi-submission or moderated items, and ranks low-attention candidates.
3. **Review**: The moderator inspects candidate posts and URLs and selects **Approve and Spotlight**, **Skip**, or **Dismiss**.
4. **Spotlight & Log**: If approved, RescueGuard applies the configured flair and sticky comment, then logs the decision in Redis.

---

## Quick Setup

1. **Install**: Add **RescueGuard** to your subreddit through the Reddit App Directory.
2. **Configure**: Open **Mod Tools > App Settings > RescueGuard**.
3. **Set Thresholds**: Configure your batch size, minimum post age, lookback days, deduplication strategy, and spotlight flair/comment text.
4. **Launch Review**: Open the subreddit menu and select **GuardHub: RescueGuard Review**.

---

## Advanced Capabilities

RescueGuard is engineered for zero-latency review queues and clean data hygiene.

- **Zero-Scan Redis Architecture**: Uses direct key lookups (`rescue:audit:<postId>`, `rescue:spotlight:<appKey>`) without expensive `KEYS *` operations.
- **Automatic TTL Expiry**: All audit keys automatically expire, preventing database clutter.
- **Logarithmic Age Dampening**: Normalizes attention scoring across older vs newer candidate submissions.
- **Graceful Error Handling**: Resilient execution with try/catch fallbacks if subreddit link flairs are disabled.

---

## Designed to Assist Moderators

RescueGuard assists moderation teams by surfacing candidate submissions for human review. RescueGuard never automatically promotes or alters posts without explicit moderator review and confirmation.

---

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

---

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/rescue-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/rescue-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
