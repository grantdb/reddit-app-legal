> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/testrank)

# TestRank 🧪

> **Empower developers to reward quality feedback, recognize dedicated beta testers, and gamify community app testing across your subreddit.**

**TestRank** is an automated tester recognition, reputation, and leaderboard engine built specifically for Android testing communities like **r/droidapptesters**. It enables app developers (OPs) to confirm helpful feedback directly from comment context menus, awards structured XP points, maintains real-time weekly and monthly leaderboards, syncs Reddit user flairs across a prestige ladder, and equips moderators with complete audit and override capabilities.

### ⚡ Key Highlights
- **Direct Developer Awards**: App creators reward testers straight from Reddit comment overflow menus with one click.
- **Automated Flair Progression**: Automatically promotes users through tiered prestige flairs (`App Explorer` → `Grandmaster Tester`) as XP climbs.
- **Live Community Leaderboards**: Spawns dedicated, interactive custom post leaderboards backed by real-time Redis Sorted Sets.
- **Cryptographic Anti-Abuse**: Prevents duplicate awards and strictly blocks self-crediting with cryptographic deduplication keys.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/testrank-flowchart.png)

### The 5-Step Recognition Pipeline

1. **Post Eligibility & Onboarding**: A developer posts an app testing thread with flair. TestRank validates eligibility and sends a deduplicated onboarding modmail with usage guidance.
2. **Tester Feedback & Activity**: Community members join tests, reply with testing feedback, bug reproductions, or bug fix confirmations.
3. **Developer Confirmation**: The developer selects **Mark Registered Tester (+5 pts)**, **Mark Helpful Feedback (+10 pts)**, **Mark Bug Found (+25 pts)**, or **Mark Fix Verified (+30 pts)** directly from the comment menu (`...`).
4. **Prestige Ladder & Flair Sync**: Redis Sorted Set leaderboards update instantly; user point totals advance toward higher prestige ranks with automatic Reddit user flair upgrades.
5. **Moderator Audit & Override Hub**: Moderators access the mod dashboard to inspect live audit logs, toggle post/user eligibility, or issue score corrections with mandatory reason logging.

---

## Quick Setup (60-Second Onboarding)

1. **Install App**: Install TestRank to your subreddit from the Reddit App Directory.
2. **Configure Settings**: Adjust point weights and onboarding modmail rules via **Mod Tools -> Apps -> testrank -> Settings**.
3. **Generate Leaderboard Post**: Open the subreddit overflow menu (`...`) and click **Create TestRank Leaderboard Post** to provision the pinned community board.
4. **Reward & Rank**: Developers click comment menus on helpful replies to confirm points and immediately trigger leaderboard and flair updates.

---

## Core Capabilities

### 1. Action Types & Point Matrix
Reward different contributions according to testing depth:
- **Registered Tester (`+5 pts`)**: Low-friction confirmation that a tester joined the Google Group, opted into the closed test, or installed the app build.
- **Helpful Feedback (`+10 pts`)**: Clear, actionable UX notes, device compatibility reports, or initial impressions.
- **Bug Found (`+25 pts`)**: Confirmed, reproducible bug reports with error logs, device specs, or screenshots.
- **Fix Verified (`+30 pts`)**: Verification confirming that a reported bug has been resolved in an updated build or patch.

### 2. Prestige Ladder & Automated Flair Sync
As testers accumulate testing points, TestRank updates their standing and automatically assigns their Reddit user flair:

| Tier | Prestige Title | Min Points | Subreddit User Flair |
| :---: | :--- | :---: | :--- |
| **1** | **App Explorer** | `0 pts` | `App Explorer` |
| **2** | **Helpful Tester** | `50 pts` | `Helpful Tester` |
| **3** | **Bug Hunter** | `150 pts` | `Bug Hunter` |
| **4** | **Elite Tester** | `350 pts` | `Elite Tester` |
| **5** | **Master Tester** | `750 pts` | `Master Tester` |
| **6** | **Grandmaster Tester** | `1,500 pts` | `Grandmaster Tester` |

### 3. Comment-Driven & Dashboard Workflows
- **Context Menu Actions**: Developers award points right inside the comment thread (`Mark Registered Tester`, `Mark Helpful Feedback`, `Mark Bug Found`, `Mark Fix Verified`).
- **Per-Post TestRank Dashboard**: OPs and mods can open **Open This Post’s TestRank Dashboard** to view all commenters on a submission and issue summary awards.
- **Opt-Out Controls**: Developers can opt out individual posts at any time by commenting `!testrank-optout`.

### 4. Moderator Governance & Audit Trail
- **Live Audit Logging**: Every award creation, reversal, and mod correction is permanently recorded in Redis with timestamps and reason strings.
- **Recreation Cooldown**: Force-recreating the leaderboard post is protected by a 5-minute spam prevention cooldown.
- **Global Toggles**: Moderators can disable awards for specific abusive users or posts while preserving historical data.

---

## The Old Way vs. The TestRank Way

| Traditional Testing Threads | With TestRank |
| :--- | :--- |
| Testers leave feedback with no acknowledgment or track record | **Verifiable reputation** and persistent community prestige |
| Developers manually replying "thanks" with no lasting recognition | **Instant one-click awards** directly from comment context menus |
| No way to identify high-quality, reliable beta testers | **Real-time leaderboards** and automated tier flairs highlighting top contributors |
| Frequent duplicate rewards and uncontrolled self-crediting | **Atomic Redis locks** and server-enforced anti-cheat safeguards |
| Moderators lacking visibility into tester activity and awards | **Comprehensive audit logging** with mandatory reason tracking on reversals |

---

## Designed to Assist Moderators & Protect Privacy

TestRank operates as an automated community utility designed to empower human moderators and developers:
- **Moderator Authority**: Moderators retain absolute authority to reverse any award, edit points, or exclude users from leaderboards.
- **Privacy & Zero PII**: TestRank never collects, stores, or transmits private personal data. All state is strictly indexed by public Reddit usernames and item IDs in isolated Redis storage.

---

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/testrank/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/testrank/PRIVACY.md)

---
*Built for Reddit's moderator community.*
