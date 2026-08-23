> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/format-guard)

# GuardHub: Format Guard

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Hardened-red?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Content_Policy-8A2BE2?style=for-the-badge)

> **Enforce clean titles, proper tags, and readable post structures automatically.**

Format Guard keeps your subreddit feed clean, consistent, and readable. Enforce character length limits, required title tags, case controls, and regex patterns with instant author guidance—all managed through an intuitive native dashboard without editing complex AutoModerator YAML.

---

## At a Glance

- **Enforce title requirements**: Mandate required bracket tags (e.g. `[Discussion]`, `[OC]`) or prefix formats.
- **Stop formatting abuse**: Detect and block all-caps yelling, excessive punctuation (`???!!!`), or clickbait structures.
- **Set length boundaries**: Define minimum and maximum character lengths for titles and post bodies.
- **Guide authors instantly**: Deliver clear automated removal reasons so users can fix and resubmit properly.
- **Test before enforcing**: Use the in-dashboard Test tab to verify formatting rules against sample submissions.

---

## The Old Way vs. The Format Guard Way

| Traditional Workflow | With Format Guard |
| :--- | :--- |
| Writing complex, fragile AutoMod regex for title tags | **Visual formatting rule builder** with clear regex options |
| Manually removing posts with all-caps screaming titles | **Automated case detection** catching uppercase abuse on submit |
| Typing repetitive mod notes explaining title rules | **Structured removal reasons** explaining exactly what rule was missed |
| Manually tracking users who repeatedly ignore formats | **Rolling 7-day violation counter** with automated modmail escalation |
| Guessing if a new regex pattern will accidentally break posts | **Interactive Test simulator** validating title strings instantly |

---

## Built for Clean Community Standards

- **Structural Constraints**: Set minimum and maximum length bounds on titles and bodies to stop one-word spam or unreadable text blocks.
- **Advanced Regex Validation**: Configure `Must Match` and `Must NOT Match` patterns to enforce custom naming schemes and forbidden phrases.
- **Case & Punctuation Control**: Automatically identify all-caps titles, alternating-case spam, and repetitive punctuation strings.
- **Instant Author Feedback**: Provide friendly, actionable removal messages so well-meaning users know how to correct their formatting.
- **Repeat Offender Escalation**: Track repeat format violations over rolling 7-day windows and notify modmail when thresholds are reached.
- **Dedicated Management Center**: Access a private dashboard from Subreddit Mod Tools to adjust rules, view match metrics, and test sample titles.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/format-guard-flowchart.png)

### Your Four-Step Workflow

1. **Submit**: A user submits a post or comment to your subreddit.
2. **Scan**: Format Guard evaluates the submission against your active structural and regex rules sequentially.
3. **Notify**: If a rule is failed, the post is removed and an automated message is sent explaining the formatting requirement.
4. **Escalate**: Repeat formatting violations are recorded in Redis and escalated to modmail when configured.

---

## Quick Setup

1. **Install**: Add **Format Guard** to your subreddit through the Reddit App Directory.
2. **Configure**: Open **GuardHub: FormatGuard Dashboard** from Subreddit Mod Tools.
3. **Create Rules**: Add your required title tags and length limits, testing them in the Test tab.
4. **Enforce**: Activate your rules to begin automated formatting validation.

*No complex AutoMod syntax required. Clean, consistent post formatting across your entire community.*

---

## Advanced Capabilities

Format Guard is built for high-speed textual analysis and robust regex evaluation across active subreddit queues.

- **Dual-Pattern Regex Engine**: Evaluates positive enforcement (`Must Match`) and negative exclusion (`Must NOT Match`) in a single pass.
- **Case Distribution Analyzer**: Measures uppercase-to-lowercase character ratios to detect yelling and alternating-case patterns.
- **Rolling Repeat Counter**: Tracks user violation frequencies over 7-day rolling windows using Redis counters.
- **In-Dashboard Regex Sandbox**: Allows moderators to test complex regular expressions against sample titles directly in the UI.

---

## Designed to Assist Moderators

Format Guard automates the validation of community stylistic and formatting standards according to the exact rules configured by your moderation team. Removal actions provide clear, actionable feedback to authors—human moderators maintain full authority to approve exceptions and adjust formatting guidelines at any time.

---

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

---

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/format-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/format-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
