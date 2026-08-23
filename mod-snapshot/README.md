> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/mod-snapshot)

# Mod Snapshot

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Hardened-red?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Archival-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Backup-8A2BE2?style=for-the-badge)

> **Backup subreddit settings, rules, and AutoMod configurations to modmail in seconds.**

Mod Snapshot provides full disaster-recovery and configuration backups for your subreddit. Capturing rules, removal reasons, flair templates, appearance settings, and AutoModerator YAML, it compiles readable, complete backup records delivered straight to your team modmail.

---

## At a Glance

- **Complete community backups**: Archive rules, removal reasons, post/user flairs, and appearance settings.
- **Full AutoMod extraction**: Back up your complete AutoModerator YAML configuration cleanly.
- **Delivered to modmail**: Receive structured markdown backup files directly in your moderation inbox.
- **Smart multi-part chunking**: Automatically splits large configurations across messages without truncating data.
- **One-tap menu triggers**: Generate fresh backups anytime from Subreddit Mod Tools.

---

## The Old Way vs. The Mod Snapshot Way

| Traditional Workflow | With Mod Snapshot |
| :--- | :--- |
| Copy-pasting rules and wiki YAML into external docs manually | **One-click complete backup** compiling every setting into clean markdown |
| Losing complex AutoMod configurations after accidental deletion | **Immutable modmail archive** providing an exact historical record |
| Searching scattered settings screens to audit subreddit rules | **Consolidated single document** capturing all community parameters |
| Truncated backups caused by Reddit modmail character limits | **Rule-aware chunking engine** splitting parts cleanly across messages |
| Forgetting when settings were last backed up | **Timestamped backup summaries** with version and metadata logging |

---

## Built for Disaster Recovery & Auditing

- **Comprehensive Configuration Capture**: Backs up community sidebar rules, removal reasons, user flairs, post flairs, appearance options, and discovered apps.
- **Full AutoModerator Archival**: Extracts raw `config/automoderator` YAML for secure offline storage, version auditing, or cross-subreddit replication.
- **Rule-Aware Chunking Engine**: Intelligently breaks large backup documents and AutoMod rules cleanly across sequential modmail threads without breaking blocks.
- **Atomic Lock & Cooldown Safeguards**: Implements a 2-minute cooldown and daily generation caps to prevent accidental burst triggering.
- **Secure Mod-Only Operation**: Available exclusively to authenticated moderators via Subreddit Mod Tools.
- **Native Settings Control**: Adjust daily snapshot generation limits and configuration preferences in App Settings.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/mod-snapshot-flowchart.png)

### Your Four-Step Workflow

1. **Trigger**: A moderator selects **Generate Mod Snapshot** from Subreddit Mod Tools.
2. **Lock**: Mod Snapshot acquires an atomic Redis lock and verifies the cooldown period.
3. **Extract**: The engine queries Reddit APIs to compile subreddit rules, removal reasons, flair templates, and AutoMod YAML.
4. **Deliver**: Formatted, rule-aware Markdown documents are dispatched directly to team modmail.

---

## Quick Setup

1. **Install**: Add **Mod Snapshot** to your subreddit through the Reddit App Directory.
2. **Configure Settings**: Open **Mod Tools > App Settings > Mod Snapshot** to review snapshot preferences.
3. **Run Backup**: Select **Generate Mod Snapshot** from Subreddit Mod Tools to create your first archive.
4. **Verify**: Open modmail to inspect your complete, structured backup document.

*No external backup servers or manual exports required. Reliable community disaster recovery inside Reddit.*

---

## Advanced Capabilities

Mod Snapshot is engineered for comprehensive configuration extraction and resilient multi-part delivery.

- **Multi-Layer Data Harvester**: Interrogates Reddit metadata endpoints to gather settings, wiki configs, flairs, and active app manifests.
- **Rule-Aware YAML Chunking**: Parses AutoMod rule boundary delimiters (`---`) to prevent splitting individual rules across message pages.
- **Atomic Concurrency Locks**: Uses Redis mutex locks to ensure only one snapshot process executes at a time.
- **Sequential Modmail Dispatch**: Transmits multi-part backup threads sequentially with delivery verification.

---

## Designed to Assist Moderators

Mod Snapshot generates complete archival records of community settings and configurations to assist teams in disaster readiness and change auditing. Backups serve as observational snapshots—human moderators retain full authority over which settings are applied or restored.

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
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/mod-snapshot/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/mod-snapshot/PRIVACY.md)

---
*Built for Reddit moderators.*
