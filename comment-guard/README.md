> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/comment-guard)

# GuardHub: Comment Guard 🛡️

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Hardened-red?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Automoderator-8A2BE2?style=for-the-badge)

> **Filter low-effort spam and keep comment threads focused and constructive.**

Comment Guard protects your comment sections from repetitive spam, low-effort demands, and copy-pasted disruptions. Using weighted pattern scoring and account trust signals, it distinguishes between spammy noise and constructive feedback—all managed from a private moderator dashboard without complex AutoModerator rules.

---

## At a Glance

- **Filter low-effort comments**: Catch repetitive demands and low-quality spam across threads.
- **Weighted pattern scoring**: Score comments using nuanced positive and negative phrase weights.
- **Factor user trust**: Give established, high-karma contributors the benefit of the doubt automatically.
- **Track repeat offenders**: Escalate persistent spammers to modmail when violation thresholds are met.
- **Inspect scoring breakdowns**: View exact pattern matches and penalty weights in your dashboard logs.

---

## The Old Way vs. The Comment Guard Way

| Traditional Workflow | With Comment Guard |
| :--- | :--- |
| Writing blunt AutoMod keyword bans that trigger false positives | **Weighted score calculation** balancing spam markers and constructive text |
| Treating brand-new throwaways and 5-year contributors identically | **Account trust adjustments** based on karma and participation history |
| Scrolling through long comment sections to find repetitive spam | **Automated background analysis** on every submitted comment |
| Manually tracking users who spam the same low-effort lines | **Repeat offender tracking** with progressive penalty escalation |
| Wondering why a comment was removed by an automated filter | **Detailed action reports** showing exact scores and matched patterns |

---

## Built for High-Quality Discussions

- **Weighted Scoring Engine**: Assign positive scores to low-effort spam patterns and negative scores to constructive markers for balanced decisions.
- **Regex Pattern Matching**: Detect disguised spam phrases, intentional misspellings, and bypass attempts with flexible regex.
- **User Trust Multipliers**: Integrate account age and karma standing to adjust sensitivity for new accounts versus trusted community regulars.
- **Repeat Offender Escalation**: Track repeat low-effort comment bursts over rolling windows and deliver alert summaries to modmail.
- **Exemption Protection**: Automatically exempt moderators, AutoModerator, and authenticated service bots from comment filtering.
- **Dedicated Management Center**: Access a private dashboard from Subreddit Mod Tools to adjust scoring thresholds, inspect logs, and test comments.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/comment-guard-flowchart.png)

### Your Four-Step Workflow

1. **Capture**: Comment Guard intercepts new comments as they are submitted across the subreddit.
2. **Verify**: The author is checked against moderator exemptions, bot lists, and user trust history.
3. **Score**: Comment text is evaluated against weighted phrase patterns to calculate a net penalty score.
4. **Action**: If the penalty exceeds your removal threshold, the comment is removed with a detailed scoring breakdown attached.

---

## Quick Setup

1. **Install**: Add **Comment Guard** to your subreddit through the Reddit App Directory.
2. **Configure**: Open **GuardHub: CommentGuard Dashboard** from Subreddit Mod Tools.
3. **Set Thresholds**: Adjust the removal score sensitivity and penalty weights to match your community standards.
4. **Monitor**: Review enforcement logs in your dashboard to refine pattern weights over time.

*No complex AutoMod rules required. Intelligent, weighted comment moderation out of the box.*

---

## Advanced Capabilities

Comment Guard is engineered for high-throughput comment stream processing with transparent scoring mechanics.

- **Weighted Pattern Matrix**: Evaluates multi-token phrase dictionaries with configurable positive and negative weight coefficients.
- **Account Trust Multiplier**: Dynamically discounts penalty scores for verified users with high subreddit karma standings.
- **Rolling Repeat Counter**: Tracks short-term comment duplication per user in Redis to apply escalating penalty modifiers.
- **Structured Report Generation**: Attaches exact scoring formulas and pattern hits to moderation reports for full auditability.

---

## Designed to Assist Moderators

Comment Guard provides weighted scoring and pattern detection to help filter low-effort spam and maintain discussion quality. Pattern scores serve as assistive signals rather than definitive proof of intent—human moderators retain complete authority to review removed comments in mod queue, approve false positives, and tune scoring sensitivity at any time.

---

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

---

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/comment-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/comment-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
