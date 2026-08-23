> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/user-guard)

# GuardHub: User Guard 🛡️

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Hardened-red?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Gatekeeper-8A2BE2?style=for-the-badge)

> **Stop throwaways, filter ban evaders, and set clear community participation thresholds.**

User Guard gives moderation teams precise control over who can participate in your subreddit. Set clear account age and karma thresholds, maintain explicit user allowlists and blocklists, and manage everything through a clean native dashboard without editing complex AutoModerator YAML.

---

## At a Glance

- **Filter new accounts**: Block day-zero throwaways and unverified accounts from flooding your feed.
- **Enforce karma requirements**: Ensure contributors have established participation history.
- **Override with identity gates**: Maintain direct username allowlists and blocklists that take instant priority.
- **Test with zero risk**: Run rules in safe Audit Mode to inspect who would match before enforcing live.
- **Control from one place**: Manage all access thresholds from a private moderator dashboard.

---

## The Old Way vs. The User Guard Way

| Traditional Workflow | With User Guard |
| :--- | :--- |
| Writing and maintaining brittle AutoMod karma rules | **Visual threshold builder** with simple sliders and inputs |
| Guessing how many legitimate users a new rule might catch | **Safe Audit Mode** logging simulated rejections in real time |
| Manually checking account age during active spam floods | **Automated account maturity gates** evaluated on submission |
| Losing track of special user exemptions across multiple rules | **Priority identity allowlists** that reliably override all filters |
| Hunting through mod log to verify why an account was blocked | **Clear rejection logs** detailing exact threshold failures |

---

## Built for Confident Community Protection

- **Maturity Thresholds**: Set minimum account age requirements to stop brand-new spam accounts before they can post.
- **Participation Gates**: Enforce combined, post, or comment karma minimums to ensure contributors have a proven track record.
- **Priority Identity Overrides**: Create exact username allowlists that always pass and blocklists that are always rejected regardless of karma.
- **Repeat Offender Escalation**: Automatically log repeat violations and deliver alert summaries to modmail when configured.
- **Safe Testing Mode**: Test strict new thresholds in Audit Mode to review simulated match logs without disrupting community activity.
- **Dedicated Management Center**: Access a private dashboard from Subreddit Mod Tools to view activity metrics, test accounts, and update rules.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/user-guard-flowchart.png)

### Your Four-Step Workflow

1. **Intercept**: User Guard receives incoming post and comment submissions from community members.
2. **Identify**: The author is checked against explicit username allowlists and blocklists for immediate priority handling.
3. **Evaluate**: If no explicit override matches, account age, karma standing, and risk score are measured against your active thresholds.
4. **Enforce**: When a threshold is failed, the configured action (`remove`, `spam`, `filter`, or `report`) is applied, or recorded quietly in Audit Mode.

---

## Quick Setup

1. **Install**: Add **User Guard** to your subreddit through the Reddit App Directory.
2. **Configure**: Open **GuardHub: UserGuard Dashboard** from Subreddit Mod Tools.
3. **Create Rules**: Add your account age and karma thresholds in Audit Mode to preview matching accounts safely.
4. **Enforce**: Switch verified rules to Live mode to begin automated gatekeeping.

*No complex YAML syntax required. Clean access controls directly in your community dashboard.*

---

## Advanced Capabilities

User Guard is engineered for reliable, high-throughput participation filtering with complete operational oversight.

- **Priority Identity Engine**: Evaluates username allowlists and blocklists first before running expensive profile calculations.
- **Multi-Factor Thresholds**: Combines account age days, total karma, post karma, and comment karma into unified or separate rules.
- **Audit Simulation Engine**: Simulates rule evaluation without modifying content, recording matches to Redis for verification.
- **Incident Logging**: Records structured audit events so your mod team can review exactly which criteria caused a filter action.

---

## Designed to Assist Moderators

User Guard automates account maturity and participation checks according to the exact thresholds set by your moderation team. Account signals and risk scores serve as assistive filters to help protect your community—human moderators maintain full authority to approve exceptions, override filter actions, and adjust rules at any time.

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
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/user-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/user-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
