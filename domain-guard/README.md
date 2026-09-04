> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/domain-guard)

# GuardHub: Domain Guard 🛡️

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Hardened-red?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Security-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Content_Policy-8A2BE2?style=for-the-badge)

> **Block harmful links, stop spam farms, and take full control of community URLs.**

Domain Guard protects your subreddit from malicious links, URL shorteners, and repeat spam domains. Define custom allowlists and blocklists, run rules in safe audit mode, and manage everything through a clean native dashboard without editing complex AutoModerator YAML.

---

## At a Glance

- **Block malicious links**: Prevent phishing and unwanted link farms across posts and comments.
- **Allowlist trusted sources**: Restrict submissions exclusively to verified, approved domains.
- **Test with zero risk**: Run new rules in Audit Mode to preview matches before enforcing them live.
- **Target by content type**: Apply separate policies to link submissions, post bodies, or comments.
- **Manage visually**: Control all domain rules through a private moderator dashboard.

---

## The Old Way vs. The Domain Guard Way

| Traditional Workflow | With Domain Guard |
| :--- | :--- |
| Writing and debugging fragile AutoMod regex patterns | **Visual domain rule builder** with instant syntax validation |
| Deploying unverified rules directly on live users | **Safe Audit Mode** that logs simulated matches without removing content |
| Manually tracking repeat domain offenders | **Automated strike escalation** and modmail alert delivery |
| Applying blunt subreddit-wide domain blocks | **Context-aware scopes** isolated to link posts, text bodies, or comments |
| Mod team guessing why a specific link was removed | **Structured incident logs** detailing exact rule matches and actions |

---

## Built for Complete URL Safety

- **Granular Domain Control**: Set strict allowlists or blocklists with automated subdomain and wildcard handling.
- **Context-Aware Scopes**: Enforce rules across link submissions, text post bodies, comment threads, or all content simultaneously.
- **Automated Filter Re-Checking & Expiration**: Automatically re-evaluates filtered posts upon edit and on schedule. Auto-approves when authors remove restricted links, automatically deletes the bot's previous moderation notification comment, unlocks the post, or auto-removes after a configurable grace period.
- **Reputation-Gated Filtering**: Apply domain restrictions exclusively to new or low-karma accounts while leaving established members unaffected.
- **Flexible Moderation Actions**: Choose between silent removal, marking as spam, filtering to mod queue, reporting, or audit-only logging.
- **Repeat Offender Escalation**: Automatically track repeated violations and escalate repeat link spammers to modmail for team review.
- **Dedicated Management Center**: Access a private dashboard from Subreddit Mod Tools to inspect metrics, adjust rules, and run test URLs.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/domain-guard-flowchart.png)

### Your Five-Step Lifecycle

1. **Extract**: Domain Guard intercepts new submissions, edits, and comments, extracting and normalizing all candidate URLs.
2. **Evaluate**: Domains are checked against global exemptions, moderator status, content scope, and user risk thresholds.
3. **Enforce**: When a restricted domain matches an active rule, the configured moderation action (`remove`, `spam`, `filter`, or `report`) executes immediately.
4. **Auto-Recheck**: Filtered submissions in the mod queue are automatically tracked and re-checked on edits (`onPostUpdate`) and recurring schedule. Cleaned posts are auto-approved, the bot's previous warning comment is deleted, and the post is unlocked; unedited posts exceeding the grace period are auto-removed.
5. **Escalate**: Repeat violations are recorded, and summary notifications are dispatched to modmail when configured.

---

## Quick Setup

1. **Install**: Add **Domain Guard** to your subreddit through the Reddit App Directory.
2. **Configure**: Open **GuardHub: DomainGuard Dashboard** from Subreddit Mod Tools.
3. **Create Rules**: Add your domain allowlist or blocklist in Audit Mode to safely verify matching behavior.
4. **Enforce**: Once satisfied with audit results, switch rules to Live mode to begin automated enforcement.

*No complex regex configuration required. Full control stays in your native dashboard.*

---

## Advanced Capabilities

Domain Guard is engineered for high-throughput link verification while giving power moderators complete operational visibility.

- **Hostname Normalization**: Automatically strips protocols, URL paths, query parameters, and port numbers to evaluate canonical hostnames.
- **Scope Isolation**: Dispatches separate checks across post link URLs, Markdown hyperlinked text, and comment bodies.
- **Risk Score Gating**: Evaluates submitting account signals (account age, karma standing) before triggering strict link enforcement.
- **Audit Simulation Engine**: Simulates policy matches in the background and stores match records in Redis for pre-deployment verification.

---

## Designed to Assist Moderators

Domain Guard automates the extraction and enforcement of domain policies according to the rules and thresholds established by your moderation team. Human moderators retain full authority to override actions, approve filtered submissions in mod queue, and adjust domain permissions at any time.

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
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/domain-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/domain-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
