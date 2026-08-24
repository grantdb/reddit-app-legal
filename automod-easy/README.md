> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/automod-easy)

# AutoMod Easy

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Hardened-red?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Dev_Suite-8A2BE2?style=for-the-badge)

> **Write, test, and optimize AutoModerator rules in a visual, safe sandbox.**

AutoMod Easy replaces error-prone YAML editing with an interactive rule builder and testing studio. Audit existing rules for safety risks, test rule configurations against dummy posts in a secure sandbox, draft curated starter templates, and safely deploy changes to your subreddit wiki with automated revision snapshots.

---

## At a Glance

- **Visual sandbox simulator**: Test AutoMod YAML against sample submissions with accurate word-boundary matching without touching live posts.
- **Rule health audit**: Inspect your active `config/automoderator` page for syntax errors, missing colons, and risk patterns.
- **Curated starter pack templates**: Rapidly customize and deploy common filter patterns for profanity, spam links, title tags, and account age gates.
- **Instant Quick-Ban form**: Ban abusive keywords with one tap from a native moderator form.
- **Automatic rollback snapshots**: Compare side-by-side diffs and restore previous configurations safely.

---

## The Old Way vs. The AutoMod Easy Way

| Traditional Workflow | With AutoMod Easy |
| :--- | :--- |
| Editing live YAML in the Reddit wiki and breaking the queue | **Isolated sandbox environment** validating rules before saving |
| Guessing how to write complex regex for tricky spam patterns | **Visual rule builder** generating clean YAML with word-boundary safeguards |
| Spending hours troubleshooting misplaced indentations | **Real-time syntax and schema linter** highlighting errors visually |
| Losing working configurations when someone makes an edit | **Automated revision snapshots** with instant one-click restores |
| Navigating through multiple wiki pages to add a single keyword | **Quick-Ban modal form** adding new filter rules in seconds |

---

## Built for Safe AutoMod Management

- **Interactive Rule Sandbox**: Experiment with rules against custom sample posts and comments without exposing your subreddit to live testing.
- **Automated Health Scorecard**: Evaluates active configuration health, flagging missing quotes, unescaped regex characters, and risky wildcards.
- **Enforceability Advisor**: Loads your community sidebar rules via Reddit API to provide code blueprints and native safety filter tips.
- **Starter Pack Templates**: Pre-configured, customizable rules for common moderation tasks including banned words, shorteners, title brackets, and age gates.
- **Configuration Diff & Restore**: Compare current YAML against previous versions with side-by-side visual diffs and one-click rollback.
- **Native Quick-Ban Form**: Add emergency keyword filters instantly via **AutoMod Easy: Quick Ban Rule** in Subreddit Mod Tools.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/automod-easy-flowchart.png)

### Your Four-Step Workflow

1. **Launch**: Open **AutoMod Easy Trainer** from Subreddit Mod Tools.
2. **Build**: Draft rules in the visual Sandbox, customize Starter Templates, or submit a Quick-Ban form.
3. **Validate**: AutoMod Easy inspects multi-document YAML syntax, validates schema keys, and tests logic against sample payloads.
4. **Deploy**: Deploy verified rules directly to your subreddit's `config/automoderator` wiki with automated snapshot backup.

---

## Quick Setup

1. **Install**: Add **AutoMod Easy** to your subreddit through the Reddit App Directory.
2. **Open Trainer**: Select **AutoMod Easy Trainer** from Subreddit Mod Tools.
3. **Audit Rules**: Review the initial health scorecard of your current AutoMod configuration.
4. **Experiment**: Use the Sandbox Lab to test new rules or verify starter templates.

*No scary live-testing mistakes. Safe, visual AutoModerator development inside Reddit.*

---

## Advanced Capabilities

AutoMod Easy is engineered for deep YAML parsing, AST validation, and safe wiki synchronization.

- **AutoMod Schema Validator**: Verifies valid rule keys, modifier combinations, and action types according to Reddit specifications.
- **Regex Safety Linter**: Detects unquoted regex characters, catastrophic backtracking risks, and syntax bugs.
- **Wiki Snapshot Engine**: Stores chronological revisions in Redis with unified diff generation and restoration endpoints.
- **Interactive React Webview**: Renders a rich desktop and mobile testing laboratory with live syntax highlighting.

---

## Designed to Assist Moderators

AutoMod Easy provides sandbox simulation and schema validation tools to assist in managing AutoModerator rules. Validation checks and rule generation serve as development aids—human moderators retain full authority over which rules are deployed, updated, or removed from their subreddit.

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
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/automod-easy/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/automod-easy/PRIVACY.md)

---
*Built for Reddit's moderator community.*
