> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/ultimate-wwe)

# Ultimate WWE Hub 🏆

> **Transform standard WWE live discussion threads into high-engagement interactive match scoreboards and prediction battlegrounds.**

Ultimate WWE Hub powers interactive, multi-match live event mega-threads for r/UltimateWWE and wrestling communities. Each custom post is tied to a specific WWE event (PLEs, Raw, SmackDown, NXT) and features an event-specific match card scoreboard, fan prediction game, dual real-time leaderboards, and a live-comments-optimized experience.

### ⚡ Key Highlights
- **Interactive Match Scoreboard**: Live card tracking match stipulations, championship indicators, match progress, and official winner banners.
- **Fan Pick 'Em Game**: Intuitive prediction ballots enabling community members to predict match outcomes before showtime with one-click locks.
- **Dual Redis Leaderboards**: Live event standings combined with persistent cumulative all-time subreddit points.
- **Universal Mobile Scrolling**: Engineered with zero-scroll-trap mobile navigation (`overscroll-behavior-y: auto`) for smooth Reddit feed browsing.

---

## How It Works

### The 4-Step Lifecycle
1. **Thread Deployment**: A moderator selects **Create WWE Live Event Thread** from the subreddit menu. The app provisions an interactive post with pre-configured or custom event cards.
2. **Pre-Show Predictions**: Before the opening bell, community members pick winners for every scheduled match. Picks are saved securely to Redis.
3. **Showtime Lock**: When the event start time is reached (or when a moderator toggles the lock), predictions lock immediately across all clients.
4. **Live Scoring & Leaderboards**: As matches conclude, moderators declare official winners. The scoring engine evaluates submitted ballots, awards points, and updates both event and cumulative subreddit leaderboards in real time.

---

## Quick Setup (60-Second Onboarding)

1. **Install**: Add **Ultimate WWE Hub** to your subreddit via the Reddit Developer portal or App Directory.
2. **Launch Thread**: From your subreddit menu, select **Create WWE Live Event Thread** to deploy an official live thread.
3. **Customize / Lock**: Open the post and use **Mod Controls** to adjust match stipulations or lock predictions at showtime.
4. **Score & Celebrate**: Declare winners as the broadcast unfolds and click **Score Event Results** to crown community winners!

---

## Core Capabilities

- 🏆 **Event Live Scoreboard**: Full match cards with championship badges, match stipulations, participant details, real-time match statuses, and official winner declarations.
- 🎯 **Pick 'Em Prediction Game**: Fans predict match winners directly inside the thread before showtime. Predictions automatically lock at bell time or on mod toggle.
- 🥇 **Dual Leaderboards**:
  - **Event Leaderboard**: Top-ranked fans for the current live show.
  - **All-Time Leaderboard**: Cumulative leaderboard tracking points across every WWE event in the subreddit.
- 💬 **Live-Discussion Optimized**: Prominent banner urging fans to sort comments by "New / Live" while the post maintains canonical scores and standings.
- 🛠️ **Reusable Mod Template**: Standardized live mega-threads for any PLE, Raw, SmackDown, or NXT show.

---

## The Old Way vs. The Ultimate WWE Hub Way

| Workflow Feature | Traditional Live Mega-Threads | With Ultimate WWE Hub |
| :--- | :--- | :--- |
| **Match Scores** | Static text edits in post body | Real-time interactive status & championship badges |
| **Prediction Ballots** | Messy comments lost in 10,000+ replies | One-click structured ballot stored in Redis |
| **Scoring & Points** | Manual spreadsheets or forgotten tallies | Automated 1-click scoring engine & leaderboards |
| **Mobile Feed Navigation** | Unresponsive embeds or clunky popups | Universal inline scrolling with native feed gestures |

---

## Designed for Subreddit Moderators

- **Moderator Authority**: Moderators retain full control over match cards, lock timing, and official winner determinations.
- **Zero PII & Sandbox Storage**: All predictions, match outcomes, and scores are processed exclusively inside Reddit's isolated, sandboxed Redis infrastructure without external third-party data collection.

---

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

---

## Legal

- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/ultimate-wwe/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/ultimate-wwe/PRIVACY.md)

---
*Built for fun on Reddit*
