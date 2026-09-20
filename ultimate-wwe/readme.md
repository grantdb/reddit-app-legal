> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/ultimate-wwe)

# Ultimate WWE Hub 🏆

> **Transform standard WWE live discussion threads into high-engagement interactive match scoreboards, championship battlegrounds, and PLE schedule hubs.**

Ultimate WWE Hub powers a synchronized multi-post ecosystem for r/UltimateWWE and wrestling communities, featuring dedicated standalone custom posts for:
1. **Live Event & Prediction Mega-Threads**: Real-time match cards, official winners, and fan prediction Pick 'Em ballots.
2. **Community Championship Belts & All-Time Leaderboards**: Pinned trophy case displaying gold championship titles (World, Intercontinental, PLE Cup, 24/7 Hardcore, Women's World), active champions, title defense histories, and season rankings.
3. **Upcoming Matches & PLE Schedule Hub**: Pinned countdown clock to the next major PLE (e.g. WrestleMania, SummerSlam, Royal Rumble), weekly show lineups (Raw on Netflix, SmackDown on USA, NXT on CW), and fan sentiment voting.

All three post types share synchronized Redis state across the subreddit so points scored in any live event immediately update championship belt holders, reign counters, and leaderboards.

### ⚡ Key Highlights
- **Multi-Post Architecture**: 3 dedicated custom post types provisioned directly from the subreddit moderator menu (`...`).
- **Interactive Match Scoreboard**: Live card tracking match stipulations, championship indicators, match progress, and official winner banners.
- **Fan Pick 'Em Game**: Intuitive prediction ballots enabling community members to predict match outcomes before showtime with one-click locks.
- **Championship Belts Trophy Case**: Automated belt defense and transfers (World Heavyweight Title to all-time #1, PLE Cup to top event scorer) with complete title reign histories.
- **PLE Countdown & Broadcast Guide**: Real-time live countdown timer to the next major event alongside weekly TV show schedules and community hype voting.
- **Cross-Post Navigation Hub**: Seamless banner links connecting fans directly between the live show thread, trophy case, and upcoming schedule.
- **Universal Mobile Scrolling**: Engineered with zero-scroll-trap mobile navigation (`overscroll-behavior-y: auto`) and 48px fine-tuned horizontal tab scrolling.

---

## How It Works

### The 4-Step Lifecycle
1. **Thread Deployment**: A moderator selects one of the 3 custom post creation menu actions (**Create WWE Live Event Thread**, **Create Championship Belts & Leaderboard Post**, or **Create Upcoming Matches & Schedule Post**).
2. **Community Engagement & Pre-Show Predictions**: Before the opening bell, community members make their picks, review the championship trophy case, and vote on upcoming show excitement.
3. **Showtime Lock**: When the event start time is reached (or when a moderator toggles the lock), predictions lock immediately across all clients.
4. **Live Scoring & Title Defenses**: As matches conclude, moderators declare official winners. The scoring engine evaluates submitted ballots, updates leaderboards, and automatically awards or defends championship belts in real time!

---

## Quick Setup (60-Second Onboarding)

1. **Install**: Add **Ultimate WWE Hub** to your subreddit via the Reddit Developer portal or App Directory.
2. **Launch Pinned Hub Posts**: From your subreddit menu (`...`), deploy the **Championship Belts & Leaderboard Post** and **Upcoming Matches & Schedule Post** as pinned community anchors.
3. **Deploy Live Event Thread**: On event night, select **Create WWE Live Event Thread** to launch the show mega-thread.
4. **Score & Crown Champions**: Declare winners as the broadcast unfolds and click **Score Event & Defend Belts** to crown champions and update community rankings!

---

## Core Capabilities

- 🏆 **Event Live Scoreboard**: Full match cards with championship badges, match stipulations, participant details, real-time match statuses, and official winner declarations.
- 🎯 **Pick 'Em Prediction Game**: Fans predict match winners directly inside the thread before showtime. Predictions automatically lock at bell time or on mod toggle.
- 👑 **Championship Belts Trophy Case**:
  - **WWE World Heavyweight Title**: Held by the #1 all-time points leader in the subreddit.
  - **Intercontinental Title**: Awarded to the current season/month workhorse predictor.
  - **PLE Main Event Cup**: Awarded live to tonight's highest-scoring fan ballot.
  - **24/7 Hardcore Community Title**: Defended across weekly shows and television threads.
  - **Complete Title History**: Track every champion, reign length (days), and successful defenses.
- 📅 **Upcoming Schedule & Live PLE Countdown**:
  - Precision countdown clock (Days, Hours, Minutes, Seconds) to the next major PLE.
  - Broadcast schedules for Monday Night Raw (Netflix), Friday Night SmackDown (USA), and WWE NXT (The CW).
  - Community hype meter voting.
- 🥇 **Dual Leaderboards**:
  - **Event Leaderboard**: Top-ranked fans for the current live show.
  - **All-Time Leaderboard**: Cumulative leaderboard tracking points across every WWE event in the subreddit.
- 🔗 **Cross-Post Community Hub**: Pinned shortcuts linking fans across all 3 WWE posts.
- 💬 **Live-Discussion Optimized**: Prominent banner urging fans to sort comments by "New / Live".

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
