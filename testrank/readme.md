> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/testrank)

# TestRank

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Utility-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Recognition_System-8A2BE2?style=for-the-badge)

> **Empower developers to reward quality feedback, recognize dedicated testers, and gamify app testing across your subreddit.**

**TestRank** is an automated tester recognition, reputation, and leaderboard engine for Android beta testing communities like **r/droidapptesters**. It allows app developers (OPs) to confirm helpful feedback directly from comment menus, awards structured XP points, maintains real-time weekly and monthly leaderboards, syncs Reddit user flairs across a prestige ladder, and equips moderators with complete audit and override capabilities.

---

## At a Glance

- **Direct Developer Recognition**: App creators reward testers straight from comment overflow menus with one click.
- **Structured 10x XP Points**: Distinct point weights for general feedback, bug reports, and fix verifications.
- **Clean Prestige Ladder**: Automatic user progression from App Explorer to Grandmaster Tester without messy emojis.
- **Automated User Flair Sync**: Syncs Reddit subreddit user flairs in real time as community members level up.
- **Public & Sticky Leaderboards**: Generates dedicated, live-updating custom post leaderboards for the community.
- **Full Moderator Oversight**: Audit trail, participation toggles, opt-out mechanisms, and manual score overrides.

---

## The Old Way vs. The TestRank Way

| Traditional Testing Threads | With TestRank |
| :--- | :--- |
| Testers leave feedback with no acknowledgment or track record | **Verifiable reputation** and persistent community prestige |
| Developers manually replying "thanks" with no lasting recognition | **Instant one-click awards** directly from comment context menus |
| No way to identify high-quality, reliable beta testers | **Real-time leaderboards** and automated tier flairs highlighting top contributors |
| Frequent duplicate rewards and uncontrolled self-crediting | **Strict idempotency keys** and server-enforced anti-cheat safeguards |
| Moderators lacking visibility into tester activity and awards | **Comprehensive audit logging** with mandatory reason tracking on reversals |

---

## Built for High-Impact Tester Recognition

- **Comment-Driven Award Flow**: Developers confirm testing feedback directly via comment menu items (**Mark Helpful Feedback**, **Mark Bug Found**, **Mark Retest**), or manage all commenters via the post dashboard.
- **Anti-Self-Credit & Deduplication**: Cryptographic dedupe keys prevent duplicate awards on the same comment and block OPs from self-crediting.
- **Automated OP Onboarding**: Sends a friendly, deduplicated modmail to the OP when an eligible testing post is submitted, explaining tools and opt-out commands.
- **Community Leaderboard Custom Posts**: Moderators can spawn dedicated, pinned custom post leaderboards that update live from Redis Sorted Sets.
- **Participation Controls**: Developers can opt out individual posts with `!testrank-optout`, while moderators can toggle post or user participation globally.
- **Immutable Audit Trail**: Logs all award creations, reversals, and manual mod corrections with mandatory reason preservation.

---

## Action Types & Point Matrix

| Action Type | XP Points | Purpose & Description |
| :--- | :---: | :--- |
| **Helpful Feedback** | `+10 pts` | Clear, actionable user feedback, UX notes, or initial testing impressions. |
| **Bug Found** | `+25 pts` | Confirmed, reproducible bug report with error details, device specs, or screenshots. |
| **Retest Verified** | `+15 pts` | Verification of an updated build confirming that a reported bug has been resolved. |

---

## Prestige Ladder & User Flair Tiers

As testers accumulate testing points, TestRank updates their standing and automatically sets their Reddit user flair:

| Level | Prestige Title | Min Points | User Flair |
| :--- | :--- | :---: | :--- |
| **Tier 1** | **App Explorer** | `0 pts` | `App Explorer` |
| **Tier 2** | **Helpful Tester** | `50 pts` | `Helpful Tester` |
| **Tier 3** | **Bug Hunter** | `150 pts` | `Bug Hunter` |
| **Tier 4** | **Elite Tester** | `350 pts` | `Elite Tester` |
| **Tier 5** | **Master Tester** | `750 pts` | `Master Tester` |
| **Tier 6** | **Grandmaster Tester** | `1,500 pts` | `Grandmaster Tester` |

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/testrank-flowchart.png)

### Your Five-Step Recognition Pipeline

1. **Post Eligibility & Onboarding**: A developer posts an app testing thread with flair. TestRank validates eligibility and sends an onboarding modmail with usage guidance.
2. **Tester Feedback & Activity**: Community members test the app build and reply with testing feedback, bug reproductions, or retest confirmations.
3. **Developer Confirmation**: The developer selects **Mark Helpful Feedback (+10 pts)**, **Mark Bug Found (+25 pts)**, or **Mark Retest (+15 pts)** from the comment menu.
4. **Prestige Ladder & Flair Sync**: Redis Sorted Set leaderboards update instantly; user point totals advance toward higher prestige ranks with automatic Reddit user flair updates.
5. **Moderator Audit & Override Hub**: Moderators access the mod dashboard to inspect live audit logs, toggle post/user eligibility, or issue score corrections with mandatory reason logging.

---

## Usage & Controls

### For App Developers (OPs)
1. Post your app testing thread in the subreddit with an appropriate link flair.
2. Review comments from testers. On helpful replies, open the comment menu (`...`) and click:
   - **Mark Helpful Feedback** (+10 pts)
   - **Mark Bug Found** (+25 pts)
   - **Mark Retest** (+15 pts)
3. Alternatively, open **Open This Post’s TestRank Dashboard** from the post overflow menu to view all post commenters and award summary cards.
4. To opt out a specific thread from TestRank, comment `!testrank-optout` on your post.

### For Community Testers
- Test apps shared in the subreddit and leave descriptive feedback.
- Track your cumulative XP, current rank, and unlocked milestone badges directly in the TestRank dashboard.
- Watch your subreddit user flair automatically upgrade as you climb the prestige ladder.

### For Subreddit Moderators
- Select **Open TestRank Mod Dashboard** from the subreddit menu to inspect real-time weekly/monthly leaderboards, toggle post or user participation, and view the immutable audit log.
- Select **Create TestRank Custom Post** to generate a pinned public leaderboard post for the community.

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
