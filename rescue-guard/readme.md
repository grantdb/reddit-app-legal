> **User Guide & Overview** | [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/rescue-guard)

# GuardHub: RescueGuard

> **Surface overlooked submissions, empower manual moderator curation, and spotlight hidden gems across your subreddit.**

RescueGuard gives moderation teams an assistive, privacy-first discovery engine to find quality community submissions from the lookback window that slipped through the cracks with low engagement. Review a ranked queue of overlooked posts and manually spotlight worthy contributions with automated post flairs and distinguished sticky notices.

---

## At a Glance

- **On-Demand Lookback Scan**: Scans recent subreddit submissions across customizable lookback windows (default: 30 days) when triggered by a moderator.
- **Engagement Velocity Ranking**: Prioritizes posts with low upvotes and low discussion counts using weighted scoring.
- **Minimum Age Filtration**: Prevents brand-new posts from surfacing before they have had natural feed exposure.
- **Single-Submission Gate**: Excludes items or apps submitted multiple times across the lookback window (`enforce_single_submission`).
- **Universal Deduplication Strategies**: Auto-detects app store package IDs, link domains, author identities, or normalized titles.
- **Moderator-in-the-Loop Review**: Zero automated highlights—human moderators maintain 100% final decision authority.

---

## How It Works: The 4-Step Operational Pipeline

### 01 · Trigger
> **Moderator-initiated dashboard launch**
> - A moderator clicks **GuardHub: RescueGuard Review Hub** in the subreddit menu to open or create the singleton Review Hub custom post.

---

### 02 · Scan & Rank
> **Lookback discovery and attention scoring**
> - RescueGuard scans submissions from the lookback window, excludes multi-submission or already-reviewed items, and ranks low-attention candidates.

---

### 03 · Review
> **Human-in-the-loop triage**
> - The moderator inspects candidate posts and URLs in the Review Hub and selects **Approve and Spotlight**, **Skip**, or **Dismiss**.

---

### 04 · Spotlight & Log
> **Automated flair, comment, and Redis audit**
> - If approved, RescueGuard applies the configured flair, pin, and sticky comment, then logs the decision in Redis.

---

## Quick Setup

1. **Install**: Add **RescueGuard** to your subreddit through the Reddit App Directory.
2. **Launch Review**: Open the subreddit menu and select **GuardHub: RescueGuard Review Hub**.
3. **Configure**: Open the **Settings** tab inside the Review Hub dashboard to set your batch size, minimum post age, lookback days, deduplication strategy, and spotlight flair/comment text.

---

## Support

> **Need Help?** Post in [https://www.reddit.com/r/grantdb](https://www.reddit.com/r/grantdb) with the app name, what you expected, what happened, and any error text or screenshots.
>
> - **User Guide**: [https://www.reddit.com/r/grantdb/wiki/rescue-guard/](https://www.reddit.com/r/grantdb/wiki/rescue-guard/)
> - **Technical Reference**: [https://www.reddit.com/r/grantdb/wiki/index/all-apps/rescue-guard/](https://www.reddit.com/r/grantdb/wiki/index/all-apps/rescue-guard/)

---

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/rescue-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/rescue-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
