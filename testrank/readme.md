> **User Guide & Overview** | [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/testrank)

# TestRank

> **Empower developers to reward quality feedback, recognize dedicated beta testers, and gamify community app testing across your subreddit.**

**TestRank** is an automated tester recognition, reputation, and leaderboard engine built specifically for Android testing communities like **r/droidapptesters**. It enables app developers (OPs) to confirm helpful feedback directly from comment context menus, awards structured XP points, maintains real-time weekly and monthly leaderboards, syncs Reddit user flairs across a prestige ladder, and equips moderators with complete audit and override capabilities.

---

## At a Glance

- **Direct Developer Awards**: App creators reward testers straight from Reddit comment overflow menus with one click.
- **Automated Flair Progression**: Automatically promotes users through tiered prestige flairs (`App Explorer` -> `Grandmaster Tester`) as XP climbs.
- **Live Community Leaderboards**: Spawns dedicated, interactive custom post leaderboards backed by real-time Redis Sorted Sets.
- **Server-Side Anti-Abuse**: Prevents duplicate awards and strictly blocks self-crediting with atomic server-side deduplication locks.

---

## How It Works: The 5-Step Operational Pipeline

### 01 · Post Eligibility & Onboarding
> **Thread validation and OP instructions**
> - A developer posts an app testing thread with flair. TestRank validates eligibility and delivers deduplicated onboarding instructions (via pinned post comment or direct message).

---

### 02 · Tester Feedback & Activity
> **Community testing and bug reporting**
> - Community members join tests and reply with testing feedback, bug reproductions, or bug fix confirmations.

---

### 03 · Developer Confirmation
> **One-click comment menu awards**
> - The developer selects **Mark Registered Tester (+5 pts)**, **Mark Helpful Feedback (+10 pts)**, **Mark Bug Found (+25 pts)**, or **Mark Fix Verified (+30 pts)** directly from the comment menu (`...`).

---

### 04 · Prestige Ladder & Flair Sync
> **Real-time Redis leaderboards and user flair updates**
> - Redis Sorted Set leaderboards update instantly; user point totals advance toward higher prestige ranks with automatic Reddit user flair upgrades.

---

### 05 · Moderator Audit & Override Hub
> **Full governance and score corrections**
> - Moderators access the mod dashboard to inspect live audit logs, toggle post/user eligibility, or issue score corrections with mandatory reason logging.

---

## Quick Setup

1. **Install App**: Install TestRank to your subreddit from the Reddit App Directory.
2. **Generate Leaderboard Post**: Open the subreddit overflow menu (`...`) and click **Create TestRank Leaderboard Post** to provision the pinned community board.
3. **Reward & Rank**: Developers click comment menus on helpful replies to confirm points and immediately trigger leaderboard and flair updates.

---

## Core Capabilities

### 1. Action Types & Point Matrix
- **Registered Tester (`+5 pts`)**: Confirmation that a tester joined the Google Group or opted into the closed test.
- **Helpful Feedback (`+10 pts`)**: Actionable UX notes, device compatibility reports, or initial impressions.
- **Bug Found (`+25 pts`)**: Confirmed, reproducible bug reports with error logs or screenshots.
- **Fix Verified (`+30 pts`)**: Verification confirming that a reported bug has been resolved in an updated build.

### 2. Prestige Ladder & Automated Flair Sync
- **Tier 1 (`0 pts`)**: `App Explorer`
- **Tier 2 (`50 pts`)**: `Helpful Tester`
- **Tier 3 (`150 pts`)**: `Bug Hunter`
- **Tier 4 (`350 pts`)**: `Elite Tester`
- **Tier 5 (`750 pts`)**: `Master Tester`
- **Tier 6 (`1,500 pts`)**: `Grandmaster Tester`

---

## Support

> **Need Help?** Post in [https://www.reddit.com/r/grantdb](https://www.reddit.com/r/grantdb) with the app name, what you expected, what happened, and any error text or screenshots.
>
> - **User Guide**: [https://www.reddit.com/r/grantdb/wiki/testrank/](https://www.reddit.com/r/grantdb/wiki/testrank/)
> - **Technical Reference**: [https://www.reddit.com/r/grantdb/wiki/index/all-apps/testrank/](https://www.reddit.com/r/grantdb/wiki/index/all-apps/testrank/)

---

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/testrank/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/testrank/PRIVACY.md)

---
*Built for Reddit's moderator community.*
