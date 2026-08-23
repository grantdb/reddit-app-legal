> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/rate-guard)

# GuardHub: Rate Guard 🛡️

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Hardened-red?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Cadence_Engine-8A2BE2?style=for-the-badge)

> **Prevent spam floods, enforce posting cooldowns, and maintain a healthy community cadence.**

Rate Guard protects your subreddit feed from rapid-fire spam floods, karma farming bursts, and excessive multi-posting. Enforce minimum cooldown gaps, rolling daily submission caps, and burst limits with automatic "next allowed post time" calculation—all configured easily within Reddit.

---

## At a Glance

- **Enforce cooldown gaps**: Require minimum time spacing (e.g. 2 hours) between consecutive submissions.
- **Set daily post caps**: Limit the total number of posts a user can submit per 24-hour window.
- **Stop burst attacks**: Detect and mitigate rapid multi-post bursts (e.g. 3 posts in 5 minutes).
- **Exact time guidance**: Automatically inform users of their exact next allowed submission time.
- **Granular exemptions**: Protect moderators, approved contributors, and specific post flairs automatically.

---

## The Old Way vs. The Rate Guard Way

| Traditional Workflow | With Rate Guard |
| :--- | :--- |
| Manually tracking how many times a user posted today | **Automated sliding window counters** tracking exact 24-hour totals |
| Scrambling during coordinated multi-post spam attacks | **Burst rate throttling** removing rapid floods within seconds |
| Manually calculating when a user is allowed to post again | **Exact time calculation** generated automatically in sticky notices |
| Writing complex timestamp parsing bots on external servers | **Native Devvit Redis engine** operating entirely within Reddit infrastructure |
| Accidental removals of daily mod announcements | **Built-in author and flair exemptions** protecting important content |

---

## Built for Balanced Posting Cadence

- **Minimum Time Gap Cooldown**: Enforce strict spacing between consecutive user submissions to prevent single authors from dominating the new queue.
- **Rolling Window Caps**: Limit total allowed posts across rolling 24-hour windows to ensure diverse community voices.
- **Burst Protection Engine**: Intercept rapid multi-submission bursts before they clutter community feeds or overwhelm mod review.
- **Clear Author Sticky Comments**: Post automated, transparent notices stating the exact cooldown remaining and next allowed posting time.
- **Comprehensive Exemptions**: Easily exempt moderators, approved submitters, or designated post flairs (such as event megathreads).
- **Privacy-First Architecture**: Stores only submission timestamps and post IDs in Redis—zero user post text or private data is ever retained.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/rate-guard-flowchart.png)

### Your Four-Step Workflow

1. **Submit**: A user submits a post to the subreddit.
2. **Verify**: Rate Guard checks author and flair exemptions (moderators, approved users, exempt post flairs).
3. **Evaluate**: If not exempt, the submission is evaluated against burst velocity limits, minimum cooldown gaps, and 24-hour caps.
4. **Enforce**: If a threshold is exceeded, Rate Guard removes the post and sticky-comments the exact next allowed submission time.

---

## Quick Setup

1. **Install**: Add **Rate Guard** to your subreddit through the Reddit App Directory.
2. **Configure**: Open **Mod Tools > App Settings > Rate Guard**.
3. **Set Cadence**: Configure your minimum time gap, 24-hour rolling cap, and burst limit thresholds.
4. **Save**: The cadence engine applies immediately to all incoming community posts.

*No external servers or complicated bot hosting required. Clean, automated rate limiting inside Reddit.*

---

## Advanced Capabilities

Rate Guard is engineered for precise sliding-window rate tracking and zero-latency submission evaluation.

- **Redis Sorted Set Timestamps**: Records submission timestamps in per-user sorted sets (`ZSET`) with sliding window score queries.
- **Burst Velocity Detection**: Evaluates submission cluster counts across short time intervals (e.g. 5-minute windows).
- **Millisecond Timestamp Arithmetic**: Accurately computes remaining cooldown milliseconds and formats localized ISO time strings.
- **Privacy-Safe Data Model**: Stores only `postId` keys and epoch timestamps, maintaining clean data hygiene and automatic TTL expiry.

---

## Designed to Assist Moderators

Rate Guard automatically enforces submission frequency and posting cadence limits according to the parameters configured by your moderation team. Cadence limits serve as assistive protections against floods—human moderators maintain full authority to approve exceptions, grant user exemptions, and adjust cadence limits at any time.

---

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

---

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/rate-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/rate-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
