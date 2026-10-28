> **User Guide & Overview** | [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/automod-easy)

# AutoMod Easy

> **Write, test, and optimize AutoModerator rules in a visual, safe sandbox.**

AutoMod Easy replaces error-prone YAML editing with an interactive rule builder and testing studio. Audit existing rules for safety risks, test rule configurations against dummy posts in a secure sandbox, draft curated starter templates, and safely deploy changes to your subreddit wiki with automated revision snapshots.

---

## At a Glance

- **Visual sandbox simulator**: Test AutoMod YAML against sample submissions with accurate word-boundary matching without touching live posts.
- **Rule health audit**: Inspect your active `config/automoderator` page for syntax errors, missing colons, and risk patterns.
- **Curated starter pack templates**: Rapidly customize and deploy common filter patterns for profanity, spam links, title tags, and account age gates.
- **One-click wiki deployment**: Deploy verified rules directly to `config/automoderator` with automated pre-mutation rollback snapshots.
- **Automatic rollback snapshots**: Compare side-by-side diffs and restore previous configurations safely from Redis-backed revision history (capped at 20 unique snapshots).

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/automod-easy-flowchart.png)

### Your Four-Step Workflow

1. **Launch**: Open **AutoMod Easy** from Subreddit Mod Tools.
2. **Build**: Draft rules in the visual Sandbox or customize Starter Templates.
3. **Validate**: AutoMod Easy inspects multi-document YAML syntax, validates schema keys, and tests logic against sample payloads.
4. **Deploy**: Deploy verified rules directly to your subreddit's `config/automoderator` wiki with automated snapshot backup.

---

---

## Built for Safe AutoMod Management

- **Interactive Rule Sandbox**: Experiment with rules against custom sample posts and comments without exposing your subreddit to live testing.
- **Automated Health Scorecard**: Evaluates active configuration health, flagging missing quotes, unescaped regex characters, and risky wildcards.
- **Enforceability Advisor**: Loads your community sidebar rules via Reddit API to provide code blueprints and native safety filter tips.
- **Starter Pack Templates**: Pre-configured, customizable rules for common moderation tasks including banned words, shorteners, title brackets, and age gates.
- **Automated Pre-Mutation Snapshots**: Every rule append, full configuration save, or restore action automatically captures a timestamped pre-mutation snapshot before touching the Reddit wiki.
- **Granular Permission Enforcement**: Modification endpoints strictly require moderators to hold `all` or `wiki` permissions before altering AutoModerator configurations.
- **Deduplicated Snapshot Storage**: Chronological snapshots are stored directly in subreddit Redis storage (capped at 20 unique snapshots, skipping identical content).

---

## Quick Setup

1. **Install**: Add **AutoMod Easy** to your subreddit through the Reddit App Directory.
2. **Open App**: Select **AutoMod Easy** from Subreddit Mod Tools.
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

## Rules Hub & Automations Compatibility Detection

Reddit is rolling out **Rules Hub and Automations**. For newly created communities or communities that have not previously used AutoMod, legacy AutoMod enforcement actions (Filter, Remove, Spam, Approve) may be disabled, making Rules Hub and Automations the primary enforcement method. Non-enforcement AutoMod functionality remains available and unchanged.

AutoMod Easy automatically detects your subreddit's active configuration and adapts its workflow:

- **Experience Detection**: Detects whether the community uses legacy AutoMod or the newer Rules Hub / Automations experience using reliable Reddit API signals with Redis caching (15-minute TTL).
- **Enforcement Gating**: For communities detected as `rules_hub`, AutoMod Easy prevents generating, appending, saving, or restoring rules whose primary purpose is an unsupported enforcement action (`action: filter`, `action: remove`, `action: spam`, `action: approve`).
- **Non-Enforcement Continuity**: Non-enforcement AutoMod features—including post and comment notifications, author messaging, moderator reporting, formatting validation, YAML parsing, sandbox simulation, and revision backups—remain fully functional.
- **Rules Hub Migration Advisor**: The dedicated **Migration** tab maps common AutoMod patterns (prohibited content removals, queue filters, link shorteners, account age gates, and keyword blockers) to suggested natural-language Rules Hub policies and Automations workflows with copyable descriptions.
- **Conservative Fallback**: If Reddit does not expose a definitive signal, AutoMod Easy conservatively treats the subreddit as `unknown` rather than assuming Rules Hub. In `unknown` mode, drafting and validation remain available, with non-blocking advisory warnings displayed prior to deploying any enforcement rule.
- **Advisor Limitations**: Migration suggestions are labeled as **recommended starting points**, not guaranteed identical equivalents. Rules Hub evaluates rule intent using natural language and semantic understanding rather than exact keyword or regex pattern matching.

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
