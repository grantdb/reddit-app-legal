> **User Guide & Overview** | [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/ultimate-wwe)

# Ultimate WWE Hub

> **Transform Monday Night Raw and Friday Night SmackDown into high-voltage, interactive live event megathreads with real-time match cards, crowd predictions, and built-in live chat.**

Ultimate WWE Hub powers a streamlined 3-post ecosystem for wrestling communities on Reddit: a pinned **WWE Belts, Stats & Upcoming Matches Hub**, a **Monday Night Raw Live Megathread**, and a **Friday Night SmackDown Live Megathread**, all backed by Redis state, Devvit realtime channels, and a synced built-in live-comments system.

---

## At a Glance

- **Streamlined 3-Post Architecture**: Provision the Belts & Stats Hub, Monday Night Raw Live Megathread, and Friday Night SmackDown Live Megathread directly from the subreddit moderator menu (`...`).
- **Live Match Cards & Crowd Predictions**: Fans lock in pre-match winner picks, track live consensus meters, trigger soundboard chants, and rate matches in real time.
- **Full-Card Management & Post-Show Recap**: Moderators can add impromptu matches or replace the entire match card in bulk, reorder or declare winners live, and publish a winner-highlighted `[SHOW RECAP]` box score at the end of the show.
- **Built-In Live Comments & Bottom Drawer**: Every Ultimate WWE custom post includes a minimal comments preview box, a 65% bottom Live Chat drawer, and a synced standard comments block below the post with reactions, own-comment deletion, reporting, and moderator pinning.

---

## How It Works: The 4-Step Operational Pipeline

### 01 · Provision the 3-Post Ecosystem

> **Deploy Hub & Weekly Live Megathreads**
> - Moderators launch **Create WWE Belts & Stats Hub Post** to pin championship lineages, superstar W-L records, and upcoming schedules.
> - On broadcast nights, moderators deploy **Create Monday Night Raw Live Megathread** or **Create Friday Night SmackDown Live Megathread** with native `LIVE` comment sorting.

---

### 02 · Pre-Show Build-Up & Card Curation

> **Set the Card & Lock Community Picks**
> - Moderators edit individual matchups, add impromptu matches, or use **Full Match Card** bulk import (including Hub schedule loading) to set or replace the full card.
> - Community members view superstar W-L records, streaks, and championship stakes, then tap to lock in pre-match winner predictions.

---

### 03 · Live Broadcast & Synced Fan Chat

> **Real-Time Ring Action & 3-Surface Live Comments**
> - When the bell rings, moderators click `[ START MATCH ]`; fans fire off crowd chants, rate match quality, and follow the Titan-Tron ticker.
> - Fans tap **Open live chat** on the minimal preview box to open the 65% bottom drawer or post in the standard comments block below the post—all synced from one canonical Redis comment store.

---

### 04 · Official Results & Post-Show Recap

> **Crown Winners, Sync Belts & Archive the Show**
> - Moderators declare winners, finish methods, and title changes, automatically updating Hub championship reigns and superstar records.
> - Once the show completes, the `[SHOW RECAP]` tab displays Match of the Night, crowd accuracy, title changes, and winner-highlighted match results.

---

## Quick Setup

1. **Install**: Add **Ultimate WWE Hub** to your subreddit via the Reddit Developer portal.
2. **Launch Anchor Hub**: From your subreddit menu (`...`), select **Create WWE Belts & Stats Hub Post** and pin it as a community anchor.
3. **Deploy Live Megathread**: On broadcast night, select **Create Monday Night Raw Live Megathread** or **Create Friday Night SmackDown Live Megathread**, then run the show from the Moderator Console.

---

## Support

> **Need help, found a bug, or have a feature request?**
> Post in **[https://www.reddit.com/r/grantdb](https://www.reddit.com/r/grantdb)** with the app name (`ultimate-wwe`), what you expected, what happened, and any error text or screenshots.
>
> - **Full User Guide**: https://www.reddit.com/r/grantdb/wiki/ultimate-wwe/
> - **Technical Reference & Settings Spec**: https://www.reddit.com/r/grantdb/wiki/index/all-apps/ultimate-wwe/

---

## Legal

- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/ultimate-wwe/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/ultimate-wwe/PRIVACY.md)

---
*Built for fun on Reddit*
