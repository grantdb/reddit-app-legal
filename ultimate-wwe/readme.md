> **User Guide & Overview** | [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/ultimate-wwe)

# Ultimate WWE Hub

> **Transform Monday Night Raw and Friday Night SmackDown into high-voltage, stadium-lit live event megathreads with interactive match cards, crowd momentum, and native Reddit Live comments.**

Ultimate WWE Hub powers a streamlined 3-post ecosystem for wrestling communities on Reddit:

1. **WWE Belts, Stats & Upcoming Matches Hub**: Pinned community anchor showcasing official WWE championship belts, superstar win/loss analytics, and an editable upcoming show schedule.
2. **WWE Monday Night Raw Live Megathread**: Crimson-neon live event megathread deployed on Monday nights with `suggestedCommentSort: 'LIVE'`, live match cards, momentum tug-of-war, and crowd chants.
3. **WWE Friday Night SmackDown Live Megathread**: Electric-blue live event megathread deployed on Friday nights with `suggestedCommentSort: 'LIVE'`, live match cards, momentum tug-of-war, and crowd chants.

---

## Key Highlights

- **Streamlined 3-Post Architecture**: 3 dedicated custom post types provisioned directly from the subreddit moderator menu (`...`).
- **Native Live Comments**: Created with `suggestedCommentSort: 'LIVE'`, keeping newest fan comments at the top throughout the broadcast while the webview manages live match state.
- **Arena Lighting & Titan-Tron Visuals**: Crimson Raw Red neon, Electric SmackDown Blue spotlights, Championship Gold plating, and victory pyro celebrations.
- **Before vs. During Match Lifecycle**:
  - *Before Match*: Contender Tale of the Tape, 1-tap pre-match winner predictions, and crowd consensus bars.
  - *During Match*: "MATCH STARTED — THE BELL HAS RUNG" alert, live momentum tug-of-war cheering, crowd chant soundboard, and 1–5 star match ratings.
  - *Match Finish*: Moderator winner declaration with golden pyro celebration, Crowd Consensus Accuracy Ribbon (prediction win % / upset alert), and "AND NEW CHAMPION!" alert.
- **Titan-Tron Live Arena Ticker**: Rolling real-time headlines broadcasting momentum surges, fan chant waves, and winner declarations.
- **Match-of-the-Night (MOTN) Honors**: Real-time crowd star ratings crown standout matches with high-contrast MOTN badges.
- **Post-Show Box Score & Trophy Case**: Inline feed card transforms into an official post-show recap upon event completion, and features a metallic Championship Trophy Case on Hub posts.
- **Moderator Live Suite**: In-arena match card customizer, 1-click impromptu match creation, reset controls, and automatic championship title belt lineage synchronization into the Hub.
- **Realtime Transport**: Powered by Devvit realtime broadcast channels paired with authoritative Redis state.

---

## How It Works

### The 3-Step Lifecycle

1. **Deployment**: On Monday or Friday afternoon, a moderator selects **Create Monday Night Raw Live Megathread** or **Create Friday Night SmackDown Live Megathread** from the subreddit menu.
2. **Pre-Show Build-Up**: Before the opening bell, community members make their picks on the match card and view live consensus meters.
3. **Showtime**: When the show begins, moderators click `[ START MATCH ]`. Fans cheer to move live momentum bars, trigger crowd chant reactions, rate match quality, and discuss the show in Reddit's native Live comment stream!

---

## Quick Setup (60-Second Onboarding)

1. **Install**: Add **Ultimate WWE Hub** to your subreddit via the Reddit Developer portal.
2. **Launch Anchor Hub**: From your subreddit menu (`...`), select **Create WWE Belts & Stats Hub Post** and pin it as a community anchor.
3. **Deploy Live Megathread**: On broadcast night, select **Create Monday Night Raw Live Megathread** or **Create Friday Night SmackDown Live Megathread**.
4. **Run the Show**: Use the moderator console to start matches and declare winners as the action unfolds!

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
