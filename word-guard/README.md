> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/word-guard)

# GuardHub: Word Guard

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Hardened-red?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Content_Policy-8A2BE2?style=for-the-badge)

> **Filter toxic words, block spam phrases, and organize keyword rules visually.**

Word Guard gives your moderation team total control over keyword filtering without complex AutoModerator YAML. Organize sensitive words into modular rule groups, test patterns safely in Audit Mode, and enforce keyword policies across posts and comments from a private dashboard.

---

## At a Glance

- **Organize by category**: Group keywords into clean buckets (e.g. Hate Speech, Scams, Spoilers).
- **Match with precision**: Choose between exact keywords, whole-word boundaries, or regex patterns.
- **Test without risk**: Run rules in safe Audit Mode to review simulated matches before live enforcement.
- **Factor user risk**: Trigger specific keyword restrictions only when author risk scores exceed thresholds.
- **Track repeat offenders**: Automatically escalate users with repeated violations to modmail.

---

## The Old Way vs. The Word Guard Way

| Traditional Workflow | With Word Guard |
| :--- | :--- |
| Editing massive, unwieldy AutoMod keyword lists | **Modular rule groups** categorized by topic and severity |
| Deploying untested keyword regex directly on live users | **Safe Audit Mode** logging simulated keyword hits quietly |
| Accidental removals caused by sub-string matching errors | **Whole-word boundary matching** preventing word-inside-word false flags |
| Manually tracking repeat keyword offenders | **Automated 7-day strike tracking** with modmail escalations |
| Mod team unsure which specific keyword triggered an action | **Detailed match records** highlighting the exact keyword and rule group |

---

## Built for Modular Content Filtering

- **Categorized Rule Groups**: Maintain independent keyword lists for hate speech, self-promotion, t-shirt scams, and spoilers.
- **Multiple Matching Modes**: Choose between simple substring matching, exact whole-word boundaries, or advanced regular expressions.
- **Reputation-Gated Rules**: Apply aggressive keyword filters exclusively to low-karma or high-risk accounts while sparing trusted regulars.
- **Safe Testing Sandbox**: Preview matches in Audit Mode to ensure clean discussions are not caught before turning enforcement live.
- **Repeat Offender Escalation**: Track repeat keyword triggers across rolling 7-day windows and notify modmail automatically.
- **Dedicated Management Center**: Access a private dashboard from Subreddit Mod Tools to manage rule groups, view metrics, and test sample phrases.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/word-guard-flowchart.png)

### Your Four-Step Workflow

1. **Extract**: Word Guard intercepts new posts and comments across submit and creation events.
2. **Verify**: Author exemptions and risk score criteria are verified before evaluating active rule groups.
3. **Scan**: Text is scanned against active keyword groups using exact, whole-word, or regex matching.
4. **Action**: If a match occurs, Word Guard executes the configured action (`remove`, `filter`, `spam`, or `report`) and logs the match.

---

## Quick Setup

1. **Install**: Add **Word Guard** to your subreddit through the Reddit App Directory.
2. **Configure**: Open **GuardHub: WordGuard Dashboard** from Subreddit Mod Tools.
3. **Create Groups**: Add your keyword groups (e.g. Scams or Profanity) and test them in Audit Mode.
4. **Enforce**: Switch verified groups to Live mode to begin automated keyword filtering.

*No cryptic YAML files required. Clean, modular keyword management directly in your community dashboard.*

---

## Advanced Capabilities

Word Guard is built for high-throughput text processing and low-latency keyword evaluation across active feeds.

- **High-Speed Keyword Index**: Evaluates multi-term dictionaries efficiently across post titles, text bodies, and comments.
- **Boundary-Aware Word Engine**: Enforces word-boundary constraints (`\b`) to prevent sub-string false positives.
- **Rolling 7-Day Strike Tracker**: Records user strike frequencies in Redis and formats structured escalation summaries for modmail.
- **Audit Mode Simulation**: Records simulated match payloads to Redis for historical review without affecting live user posts.

---

## Designed to Assist Moderators

Word Guard automates keyword and phrase filtering according to the exact dictionaries and thresholds defined by your moderation team. Keyword matches serve as assistive filters—human moderators maintain full authority to approve filtered content in mod queue, whitelist false positives, and adjust keyword rules at any time.

---

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

---

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/word-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/word-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
