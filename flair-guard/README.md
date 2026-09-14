# Flair Guard 🛡️

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Hardened-red?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Community_Styling-8A2BE2?style=for-the-badge)

> **Automate post flair assignment to keep your community organized and searchable.**

Flair Guard ensures your subreddit stays visually structured and searchable by automatically applying post flairs upon submission based on title keywords. Built on the GuardHub eligibility-first architecture, it verifies that submissions remain active, approved, and spam-free before applying flairs—all configured directly through native Reddit Mod Tools without fragile AutoModerator rules.

---

## At a Glance

- **Automated Post Flairing**: Categorize submissions automatically based on title keywords.
- **Eligibility-First Gate**: Configurable delay timer (5–100s) confirms submissions are not removed, filtered, or marked as spam before acting.
- **Moderator Exemption**: Protect moderator announcements and mod-submitted posts from automated flair overwrites.
- **Atomic Deduplication**: Redis-backed concurrency locks prevent duplicate processing during platform trigger retries.
- **Native Devvit Settings**: Configure keywords and flair template IDs directly in Subreddit Mod Tools.

---

## The Old Way vs. The Flair Guard Way

| Traditional Workflow | With Flair Guard |
| :--- | :--- |
| Manually flairing dozens of untagged posts every day | **Automated rule-based flairing** applied accurately after submission |
| Writing complex AutoMod regex for flair template IDs | **Clean settings configuration** linking keywords to flair template UUIDs |
| Sending repetitive modmail reminders for missing flairs | **Instant automated categorization** without user friction |
| Flairs applied to posts immediately deleted by spam filters | **Eligibility gate** checks post status after safety pipeline before flairing |
| Inconsistent flair styling across different moderators | **Uniform community organization** enforced with 100% consistency |

---

## Built for Effortless Content Organization

- **Keyword Matching**: Automatically assign a designated post flair when submission titles contain configured trigger keywords.
- **GuardHub Delayed Processing**: Waits a configurable duration (default: 20 seconds) before checking eligibility, ensuring Reddit's spam filters and AutoMod have completed their initial evaluations.
- **Safety Gate Checks**: Optionally skip posts that are removed, marked as spam, or held in the modqueue awaiting approval.
- **Deduplication Safeguards**: Atomic Redis scheduling locks prevent race conditions between `PostSubmit` and `PostCreate` triggers.
- **Moderator Exemption**: Automatically skip submissions authored by subreddit moderators.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/flair-guard-flowchart.png)

### Your Four-Step Workflow

1. **Trigger Ingestion & Deduplication**: A user submits a post. `PostSubmit` or `PostCreate` triggers receive the event and acquire an atomic Redis scheduling lock.
2. **Delayed Eligibility Gate**: After a configurable delay (5–100 seconds), Flair Guard verifies the post is still live and checks moderator exemptions, removal status, spam markers, and modqueue filtering.
3. **Keyword Scanner**: For eligible posts, the scanner checks the submission title against your configured comma-separated keywords.
4. **Post Flair Enforcement**: When keywords match, the target post flair template ID is applied via Reddit API, a 90-day deduplication token is stored in Redis, and structured lifecycle logging records the action.

---

## Quick Setup

1. **Install**: Add **Flair Guard** to your subreddit through the Reddit App Directory.
2. **Configure**: Open **Mod Tools > App Settings > Flair Guard**.
3. **Set Template ID**: Paste your subreddit post flair template UUID into **Target Post Flair Template ID**.
4. **Define Keywords**: Enter comma-separated trigger keywords (e.g. `urgent, help, question`).
5. **Save**: Automated flair enforcement begins immediately on all incoming community posts.

*No complex AutoMod YAML required. Clean visual organization for your entire community.*

---

## Configuration Options

| Setting | Type | Default | Description |
| :--- | :--- | :--- | :--- |
| `delayedProcessingEnabled` | Boolean | `true` | Enables eligibility-first delay gate before flairing |
| `delayedProcessingSeconds` | Number | `20` | Seconds to wait before checking post eligibility (5–100s) |
| `skipIfRemoved` | Boolean | `true` | Skips processing if the post was removed during delay |
| `skipIfFiltered` | Boolean | `true` | Skips processing if the post is awaiting modqueue approval |
| `skipIfSpam` | Boolean | `true` | Skips processing if the post was marked as spam |
| `moderatorExempt` | Boolean | `true` | Exempts moderator submissions from automated flairing |
| `triggerKeywords` | String | `urgent, help, question` | Comma-separated trigger keywords matched against post title |
| `targetPostFlairId` | String | `""` | Target post flair template UUID to apply on match |

---

## Designed to Assist Moderators

Flair Guard automates post flair categorization according to the exact mappings defined by your moderation team. Automated flairs serve as organization tools—human moderators maintain full authority to edit, override, remove, or reassign flairs at any time.

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
