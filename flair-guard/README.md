> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/flair-guard)

# GuardHub: Flair Guard

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Hardened-red?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Community_Styling-8A2BE2?style=for-the-badge)

> **Automate post and user flair assignment to keep your community organized.**

Flair Guard ensures your subreddit stays visually structured and searchable by automatically applying post and user flairs. Map keywords, domain links, and author participation standing to specific flair templates—all configured through clean native settings without fragile AutoModerator rules.

---

## At a Glance

- **Automate post flairing**: Categorize submissions automatically based on title keywords and link domains.
- **Dynamic user badges**: Apply user flairs based on contributor reputation, verified status, or milestone criteria.
- **Keep feeds searchable**: Ensure consistent flair categorization across all community submissions.
- **Reduce mod queue cleanup**: Stop manually flairing untagged posts or sending flair reminder messages.
- **Native Devvit settings**: Configure all template mappings directly from Subreddit Mod Tools.

---

## The Old Way vs. The Flair Guard Way

| Traditional Workflow | With Flair Guard |
| :--- | :--- |
| Manually flairing dozens of untagged posts every day | **Automated rule-based flairing** applied immediately upon submission |
| Writing complex AutoMod regex for flair template IDs | **Clean settings configuration** linking keywords to flair templates |
| Sending repetitive modmail reminders for missing flairs | **Instant automated categorization** without user friction |
| Inconsistent flair styling across different moderators | **Uniform community organization** enforced with 100% consistency |
| Mod team manually updating user status flairs | **Automated reputation-based flairing** based on author standing |

---

## Built for Effortless Content Organization

- **Keyword-to-Flair Mapping**: Automatically assign specific post flairs when submission titles contain designated trigger words or tags.
- **Domain-Based Categorization**: Apply custom link flairs based on destination URL hostnames (e.g. News, Video, Official Source).
- **Dynamic User Badges**: Assign specialized user flairs to recognize established community contributors or highlight verified members.
- **Deduplication Safeguards**: Built-in atomic locking prevents duplicate flair applications during platform trigger retries.
- **Author & Moderator Exemptions**: Protect mod announcements and custom author flairs from being overwritten.
- **Seamless Settings Management**: Configure all template IDs and matching rules directly from Subreddit Mod Tools.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/flair-guard-flowchart.png)

### Your Four-Step Workflow

1. **Submit**: A user submits a new post to the subreddit.
2. **Scan**: Flair Guard scans the title, text body, and link domain against your active flair mapping rules.
3. **Apply**: When matching criteria are met, the specified Post Flair or User Flair template is applied immediately.
4. **Log**: Enforcement actions are recorded for transparent audit and history tracking.

---

## Quick Setup

1. **Install**: Add **Flair Guard** to your subreddit through the Reddit App Directory.
2. **Configure**: Open **Mod Tools > App Settings > Flair Guard**.
3. **Map Flairs**: Enter your keyword triggers and corresponding flair template IDs.
4. **Save**: Automated flair enforcement begins immediately on all incoming community posts.

*No complex AutoMod YAML required. Clean visual organization for your entire community.*

---

## Advanced Capabilities

Flair Guard is engineered for fast pattern matching and reliable flair assignment across active subreddit queues.

- **Multi-Factor Rule Engine**: Matches against post titles, URL hostnames, and body text patterns in a single evaluation.
- **Atomic State Locking**: Prevents race conditions and multiple flair overwrites during concurrent trigger events.
- **Template ID Resolution**: Directly integrates with native Reddit flair template GUIDs for precise color and styling retention.
- **Execution Logging**: Records all flair assignment events in Redis for review and operational oversight.

---

## Designed to Assist Moderators

Flair Guard automates post and user flair categorization according to the exact mappings defined by your moderation team. Automated flairs serve as organization tools—human moderators maintain full authority to edit, override, remove, or reassign flairs at any time.

---

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

---

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/flair-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/flair-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
