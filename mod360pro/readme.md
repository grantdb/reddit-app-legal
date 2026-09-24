> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/mod360pro)

# Mod360 Pro

> **The all-in-one Reddit moderation control center. Sub-10ms spam gates, deep multi-rule content evaluation, timed quarantine, and two-way wiki sync in a single unified engine.**

Mod360 Pro replaces fragmented moderation bots and competing sticky comments with one coherent, high-speed moderation pipeline. Manage keyword filters, domain policies, sliding-window rate limits, user verification tiers, reputation scoring, and disaster backups from a single native dashboard.

---

## At a Glance

- **Sub-10ms Pre-AutoMod Gate**: Intercepts spam floods, suspended accounts, and duplicate posts on `onPostSubmit` before content enters the community.
- **Deep Multi-Rule Content Engine**: Evaluates domain policies, keyword regexes, author verification, and topic guides on `onPostCreate`.
- **Timed Quarantine State Machine**: Holds marginal posts in a temporary quarantine (15m–48h) with automated expiration timers and 1-click mod release.
- **Single Consolidated Sticky Notice**: Groups all rule violations into exactly one clean markdown notice. Zero bot comment clutter.
- **0–100 Reputation Safety Score**: Instant algorithmic trust score computed from account age, karma ratio, verified email, and domain history.
- **In-Feed Mod Quick Actions**: Instant context menu tools (`Check Reputation`, `Quick Approve`, `Quick Remove`, `Export Backup to Modmail`) on every post.
- **False-Positive Rescue Hub**: Dedicated triage interface in the dashboard for instant 1-click restoration and rule tuning.
- **Two-Way Wiki Policy Sync**: Bi-directional rule synchronization with `r/subreddit/wiki/mod360_rules` for effortless team collaboration.
- **Disaster Recovery Modmail Backups**: 1-click snapshot exporting the entire active configuration directly to mod team Modmail.

---

## Execution Pipeline & Action Matrix

| Pipeline Stage | Event Trigger | Evaluation Scope | Standard Latency | Default Action |
| :--- | :--- | :--- | :--- | :--- |
| **Stage 1: Pre-Filter** | `onPostSubmit` | Suspended / shadowbanned users, duplicate hashes, sliding-window rate limits | `< 8ms` (Redis-only) | Immediate Reject & Filter |
| **Stage 2: Deep Evaluation** | `onPostCreate` | Domain allow/blocklists, regex keywords, title format rules, email verification | `< 35ms` | Atomic Removal & Lock |
| **Stage 3: Timed Quarantine** | Post Evaluation | Marginal domains, new user threshold edge-cases, flagged link shorteners | Instant State Transition | Hold with Countdown Timer |
| **Stage 4: Topic Guide Match** | Clean Submissions | Community FAQ keywords, guide tags, resource suggestions | Non-blocking | Suggest Resource Wiki |
| **Stage 5: Notice & Audit** | Violations Detected | Markdown notification consolidation, rescue log capture, atomic lock | Synchronous | Single Sticky Notice |

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/mod360pro-flowchart.png)

### The 5-Step Operational Flow

1. **Fast-Gate Interception (`onPostSubmit`)**: Incoming submissions pass through an atomic Redis gate in single-digit milliseconds, blocking known spam rings, banned authors, and rapid-fire flood bursts.
2. **Deep Content Inspection (`onPostCreate`)**: Surviving posts undergo modular inspection across keyword lists, domain rules, title compliance, and author verification tiers.
3. **Quarantine or Verdict**: Clear violations trigger immediate removal with concurrency locks (`SET NX`); borderline posts enter the timed quarantine state machine awaiting manual review or auto-expiry.
4. **Single-Notice Dispatch**: Violations are assembled into a single formatted sticky comment detailing exact community guidelines violated and appeal steps.
5. **Rescue Hub Logging**: Removed items are archived into the in-dashboard Rescue Hub, allowing any moderator to reverse false positives with one click.

---

## Core Features

### High-Speed Spam & Flood Defense
- **Sliding-Window Frequency Limiter**: Configurable post-per-minute counters that clamp burst submissions and coordinated spam floods.
- **Duplicate Content Fingerprinting**: Per-subreddit hash caching that catches identical link and text spam across multiple accounts.
- **Suspended & Shadowban Filter**: Real-time user API check identifying deleted or suspended accounts before they clutter the moderation queue.

### Deep Content Policies
- **Domain & URL Shortener Guard**: Native detection for link shorteners, tracking parameters, chat links, and blacklisted domains.
- **Multi-Group Keyword & Regex Engine**: Case-insensitive matching, word boundaries, and customizable match thresholds with built-in test simulators.
- **Author Verification Tiers**: Restrict posting privileges based on verified email requirements, subreddit flair templates, or minimum karma milestones.

### ⏱️ Timed Quarantine State Machine
- **Configurable Countdown Windows**: Hold flagged items for 15m, 30m, 1h, 2h, 4h, 8h, 24h, or 48h.
- **Auto-Expiration Handling**: Unreviewed items in quarantine automatically expire to permanent removal once the timer concludes.
- **1-Click Mod Release**: Release and approve quarantined items directly from the mod dashboard or feed action menu.

### 📊 In-Feed Moderator Tools & Reputation Score
- **0–100 Community Safety Score**: Calculated from author age, karma ratios, email verification, and community post history.
- **Native Post & Comment Menu Actions**:
  - `Check Reputation`: Displays comprehensive trust breakdown and violation count.
  - `Quick Approve`: Approves content and clears pending quarantine timers.
  - `Quick Remove`: Removes post with optional preset removal reason.
  - `Export Backup to Modmail`: Dispatches full encrypted config snapshot to modmail.

### 🔄 Wiki Sync & Disaster Recovery
- **Two-Way Wiki Synchronization**: Edit your rules in `r/subreddit/wiki/mod360_rules` or in the visual dashboard; changes sync bi-directionally.
- **Encrypted Modmail Snapshots**: Export complete configuration snapshots directly to Subreddit Modmail for permanent, tamper-proof archival.
- **Zero-Risk Shadow Mode**: Run new rules in passive shadow mode with audit logging before switching them to active live enforcement.

---

## Quick Setup (60 Seconds)

1. **Install**: Add **Mod360 Pro** to your subreddit from the Reddit App Directory.
2. **Open Control Center**: Navigate to **Mod Tools > Mod360 Pro Dashboard**.
3. **Verify Settings in Shadow Mode**: Test rules and run simulations using the in-dashboard test benches.
4. **Switch to Live Enforcement**: Toggle operational status to **Live** in the Overview tab.

---

## Dashboard Specifications

| Control Tab | Core Functions | Direct Moderator Action |
| :--- | :--- | :--- |
| **Overview** | System health, operational mode toggle, recent event counters | Switch between Shadow and Live modes |
| **Rules Engine** | Keyword patterns, regex groups, title syntax validation | Add, edit, or test keyword rules |
| **Domains** | URL allowlists, domain blocks, shortener detection | Manage link and domain policies |
| **Quarantine** | Active quarantine queue, countdown timers, pending releases | Approve or expire quarantined posts |
| **Verification** | Karma minimums, account age gates, flair requirements | Adjust community onboarding tiers |
| **Rescue Hub** | False-positive triage, 1-click restore, whitelist author | Restore wrongly flagged content |
| **Wiki Sync** | Bi-directional wiki editor, version comparison, sync status | Push or pull rules to subreddit wiki |
| **Backups** | Snapshot creation, modmail export, configuration restore | Generate permanent modmail backup |

---

## Designed to Assist Moderators

Mod360 Pro is built strictly on human-in-the-loop principles. All automated actions are transparent, auditable, and fully reversible:
- **No Black Box AI**: Clear rule matches and explicit logic paths.
- **Zero PII Storage**: Only standard Reddit IDs and metadata are processed; no personal identifiable data is ever collected or stored.
- **Moderator Authority**: Human moderators retain full authority to override, release, approve, or reconfigure any rule at any time.

---

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include:
- The app name (`mod360pro`).
- What you expected to happen.
- What happened instead.
- Any error message.
- Screenshots or relevant details.

---

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/mod360pro/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/mod360pro/PRIVACY.md)

---
*Made for Mods to mod*
