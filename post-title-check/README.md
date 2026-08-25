> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/post-title-check)

# Post Title Check

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Hardened-red?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Content_Policy-8A2BE2?style=for-the-badge)

> **Enforce editorial standards, require title tags, and guide authors automatically.**

Post Title Check ensures your subreddit feed stays readable, informative, and clean. Validating submission titles against word counts, bracket tags, banned phrases, and character sets, it delivers instant, friendly removal feedback so authors can fix their titles and resubmit.

---

## At a Glance

- **Enforce title requirements**: Mandate required category brackets (e.g. `[News]`, `[OC]`, `[Guide]`).
- **Set minimum word counts**: Prevent lazy, vague titles like "Help" or "Look at this".
- **Block clickbait phrases**: Automatically filter clickbait terms, spoilers, or prohibited phrases.
- **Copy & Resubmit guidance**: Provide authors with their original text and clear instructions to fix formatting.
- **Distinguished sticky notices**: Leave clear, public removal comments explaining community guidelines.

---

## The Old Way vs. The Post Title Check Way

| Traditional Workflow | With Post Title Check |
| :--- | :--- |
| Writing complex AutoMod regex for title formatting | **Clean settings toggles** for word counts, tags, and banned words |
| Manually removing vague one-word post titles | **Instant automated validation** on every new submission |
| Typing repetitive mod comments explaining title rules | **Dynamic template messages** with `{phrase}` and `{minWordCount}` |
| Frustrated users asking modmail why their post was removed | **Private author message** with a ready-to-use "Copy & Resubmit" snippet |
| Accidental removal of daily moderator announcements | **Built-in moderator exemption toggle** bypassing checks automatically |

---

## Built for Clean Community Feeds

- **Comprehensive Rule Engine**: Validate minimum word counts, required bracket prefixes, banned phrases, and ASCII-only character sets.
- **Dynamic Removal Reasons**: Configure custom explanations with dynamic placeholders (`{phrase}`, `{minWordCount}`) for precise author feedback.
- **Author Education & Guidance**: Delivers a structured private message to authors containing their original submission text and clear correction tips.
- **Distinguished Mod Comments**: Posts a distinguished, locked sticky comment on removed submissions for public community transparency.
- **Moderator Exemption Controls**: Allow mod posts and official announcements to bypass title formatting rules seamlessly.
- **Native Settings Control**: Configure all rules and custom messages directly within Subreddit Mod Tools.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/post-title-check-flowchart.png)

### Your Four-Step Workflow

1. **Submit**: A user submits a new post to the subreddit.
2. **Evaluate**: Post Title Check evaluates the title against active formatting, word count, and banned phrase rules.
3. **Action**: If a violation is detected, the post is removed and a distinguished sticky comment is published.
4. **Guide**: The author receives a private message with their original text and instructions to correct and resubmit.

---

## Quick Setup

1. **Install**: Add **Post Title Check** to your subreddit through the Reddit App Directory.
2. **Configure Rules**: Open **Mod Tools > App Settings > Post Title Check** to set word counts and required tags.
3. **Add Banned Words**: Enter prohibited clickbait phrases separated by commas.
4. **Save**: Automated title validation begins immediately on all incoming community submissions.

*No complex AutoMod regex scripts required. Clean, professional titles across your entire feed.*

---

## Advanced Capabilities

Post Title Check is engineered for low-latency title parsing and resilient event handling.

- **Multi-Factor Title Parser**: Evaluates word counts, bracket delimiters, character sets, and phrase lists in a single pass.
- **Dynamic String Template Engine**: Replaces variables in custom removal reasons with the exact phrase or limit violated.
- **Effectively-Once Execution Mutex**: Uses Redis locks to prevent duplicate enforcement actions during Reddit platform retries.
- **Eligibility-First Gate**: Verifies submission eligibility before firing notification messages to ensure clean operations.

---

## Designed to Assist Moderators

Post Title Check automates submission title validation according to the exact standards set by your moderation team. Validation rules serve as assistive quality controls—human moderators maintain complete authority to review removed posts, approve exceptions, and adjust title criteria at any time.

---

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include:
- The app name.
- What you expected to happen.
- What happened instead.
- Any error message.
- Screenshots or relevant details.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/post-title-check/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/post-title-check/PRIVACY.md)

---
*Built for Reddit's moderator community.*
