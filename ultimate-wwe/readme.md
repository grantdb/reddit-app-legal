> **User Guide & Overview** | [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/ultimate-wwe)

# Ultimate WWE Hub

> **Transform standard WWE live discussion threads into high-engagement interactive match scoreboards, championship battlegrounds, and PLE schedule hubs.**

Ultimate WWE Hub powers a synchronized multi-post ecosystem for r/UltimateWWE and wrestling communities, featuring three dedicated custom post triggers:

1. **WWE Live Event Mega-Thread**: Created for that day's live show (PLE or weekly TV) featuring official match cards, wrestlers scheduled, live community pick consensus meters, direct jump links to the Superstar Stats & Belts Hub, and integrated live discussion callouts for Reddit comments.
2. **Superstar Stats, Records & Championship Belts Hub**: Complete wrestler center displaying 2026 season win/loss records, win percentages, streaks, Tale of the Tape comparisons, and official WWE championship belts (Undisputed WWE, World Heavyweight, Women's World, WWE Women's, Intercontinental, US Championship, Tag Team, and NXT) with real titleholders and reign histories. Zero community leaderboards or fan points inside this wrestler showcase!
3. **Community Prediction & Picking Board**: Dedicated hub for community guessing, Pick 'Em ballots, live event rankings, and all-time subreddit prediction leaderboards.

All posts share synchronized Redis state across the subreddit and feature direct cross-post navigation so fans can seamlessly jump between stats, picks, and live event threads.

## Key Highlights

- **Streamlined 3-Trigger Architecture**: 3 dedicated custom post types provisioned directly from the subreddit moderator menu (`...`).
- **Unified Wrestler Hub**: Superstar stats, win/loss records, tale of the tape, streaks, and official WWE championship belts combined into one comprehensive showcase.
- **Official WWE Championship Lineage**: Authentic WWE titleholders (Cody Rhodes, Gunther, Liv Morgan, Nia Jax, Bron Breakker, LA Knight, The Judgment Day, Motor City Machine Guns, Trick Williams) with real reign days, brand badges, and defense counts.
- **Live Community Pick Consensus**: Event match cards calculate and display real-time community pick percentage breakdowns so fans see who the subreddit favors before bell time.
- **Live Chat Integration**: Direct prompt and jump controls directing discussion to Reddit comments sorted by "Live" or "New".
- **Dedicated Community Picking Board**: Fan guessing, ballots, and leaderboards housed cleanly in their own dedicated thread.
- **Universal Mobile Scrolling**: Engineered with zero-scroll-trap mobile navigation (`overscroll-behavior-y: auto`) and 48px fine-tuned horizontal tab scrolling.

---

## How It Works

### The 3-Step Lifecycle

1. **Thread Deployment**: A moderator selects one of the 3 custom post creation menu actions (**Create WWE Live Event Thread**, **Create Superstar Stats, Records & Belts Post**, or **Create Community Prediction & Picking Board**).
2. **Community Engagement & Pre-Show Predictions**: Before the opening bell, community members make their picks on the Picking Board, explore wrestler analytics and championship belts on the Superstar Hub, and view live pick consensus on the match card.
3. **Showtime & Live Chat**: When the event begins, fans follow match statuses, participate in live chat via Reddit comments, and moderators score official results to update community leaderboards!

---

## Quick Setup (60-Second Onboarding)

1. **Install**: Add **Ultimate WWE Hub** to your subreddit via the Reddit Developer portal or App Directory.
2. **Launch Pinned Hub Posts**: From your subreddit menu (`...`), deploy the **Superstar Stats, Records & Belts Post** and **Community Prediction & Picking Board** as pinned community anchors.
3. **Deploy Live Event Thread**: On event night, select **Create WWE Live Event Thread** to launch the show mega-thread with live match cards, community pick consensus, and live chat.
4. **Score & Crown Champions**: Declare winners as the broadcast unfolds and click **Score Event Results** to update community rankings!

---

## Core Capabilities

- **Event Live Scoreboard**: Full match cards with championship badges, match stipulations, participant details, real-time match statuses, and official winner declarations.
- **Community Pick Consensus**: Dynamic percentage meters displaying the subreddit's predictions across each match.
- **Official Championship Belts Trophy Case**:
  - **Undisputed WWE Championship**: Held by Cody Rhodes (SmackDown).
  - **World Heavyweight Championship**: Held by Gunther (Raw).
  - **Women's World Championship**: Held by Liv Morgan (Raw).
  - **WWE Women's Championship**: Held by Nia Jax (SmackDown).
  - **WWE Intercontinental Championship**: Held by Bron Breakker (Raw).
  - **WWE United States Championship**: Held by LA Knight (SmackDown).
  - **Tag Team & NXT Championships**: World Tag Team, WWE Tag Team, and NXT Championship with complete reign lineage.
- **Dedicated Community Picking Board**:
  - Intuitive ballots for guessing match winners.
  - Current event leaderboard and cumulative all-time subreddit points table.
- **Cross-Post Hub Navigation**: Pinned shortcuts linking fans directly to the Superstar Stats & Belts Hub.
- **Live Comment Discussion**: Quick action jumping fans to Reddit comments for real-time live chat.

---

## Designed for Subreddit Moderators

- **Full Match Card Authority**: Moderators can create, edit (participants, stipulations, titles, championship status, points), and delete matches across both live event threads and future upcoming shows.
- **Dynamic Upcoming Schedule Management**: Add upcoming PLEs and TV specials, update broadcast dates and networks, adjust countdown target timestamps, manage fight card lineups, or restore official WWE calendar defaults with one click.
- **Zero PII & Sandbox Storage**: All predictions, match outcomes, custom schedule edits, and scores are processed exclusively inside Reddit's isolated, sandboxed Redis infrastructure without external third-party data collection.

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
