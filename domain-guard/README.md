> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/domain-guard)

# GuardHub: Domain Guard 🛡️

> **Block harmful links, stop spam farms, and take full control of community URLs.**

Domain Guard protects your subreddit from malicious links, URL shorteners, and repeat spam domains. Define custom allowlists and blocklists, run rules in safe audit mode, and manage everything through a clean native dashboard without editing complex AutoModerator YAML.

### ⚡ Key Highlights
- **Automated Mod Approval Recognition**: Recognizes when moderators approve submissions directly on Reddit, safeguarding approved content from subsequent false removals.
- **Granular Domain Control**: Set strict allowlists or blocklists with automated subdomain and wildcard handling across link posts, body text, and comments.
- **Intelligent Auto-Recheck & Expiration**: Automatically re-checks filtered queue submissions when authors edit out restricted links, auto-approves clean revisions, and deletes warning comments.
- **Safe Risk-Free Audit Mode**: Test and simulate new domain rules in background audit mode with live match logging before turning on real removals.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/domain-guard-flowchart.png)

### The 5-Step Lifecycle

1. **Extract**: Domain Guard intercepts new submissions, edits, and comments, extracting and normalizing all candidate URLs.
2. **Evaluate**: Domains are checked against global exemptions, moderator status, content scope, and user risk thresholds.
3. **Enforce**: When a restricted domain matches an active rule, the configured moderation action (`remove`, `spam`, `filter`, or `report`) executes immediately.
4. **Auto-Recheck & Approval Recognition**: Filtered submissions in the mod queue are automatically tracked and re-checked on edits (`onPostUpdate`) and recurring schedule. When a moderator approves a post or an author cleans up restricted links, the post is protected, the warning comment is removed, and the thread is unlocked.
5. **Escalate**: Repeat violations are recorded, and summary notifications are dispatched to modmail when configured.

---

## Quick Setup (60-Second Onboarding)

1. **Install**: Add **Domain Guard** to your subreddit through the Reddit App Directory.
2. **Open Dashboard**: Launch **GuardHub: DomainGuard Dashboard** from Subreddit Mod Tools or the subreddit menu.
3. **Configure Rules**: Add your domain allowlist or blocklist in Audit Mode to safely verify matching behavior.
4. **Enforce**: Once satisfied with audit results, switch rules to Live mode to begin automated enforcement.

*No complex regex configuration required. Full control stays in your native dashboard.*

---

## Core Capabilities

- **Context-Aware Scopes**: Dispatches separate checks across post link URLs, Markdown hyperlinked text, and comment bodies.
- **Human Moderator Primacy**: Listens to native moderation actions (`onModAction`) so manual approvals are permanently respected and never overridden by subsequent edits.
- **Reputation-Gated Filtering**: Apply domain restrictions exclusively to new or low-karma accounts while leaving established members unaffected.
- **Repeat Offender Escalation**: Automatically track repeated violations and escalate repeat link spammers to modmail for team review.
- **Dedicated Management Center**: Access a private dashboard from Subreddit Mod Tools to inspect metrics, adjust rules, and run test URLs.

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

## Designed to Assist Moderators & Privacy

Domain Guard is built strictly to assist human moderation teams. Domain policies are enforced only according to rules explicitly configured by moderators. Human moderators retain full authority to override actions and approve content at any time. Domain Guard does not store user private messages or personally identifiable information (zero PII).

---

## Support

For help, bug reports, or feature requests, post in r/grantdb.  
Please include:
- The app name (`domain-guard`).
- What you expected to happen.
- What happened instead.
- Any error message.
- Screenshots or relevant details.

---

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/domain-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/domain-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
