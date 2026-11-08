> **User Guide & Overview** | [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/ultimate-wwe)

# Ultimate WWE Hub

> **Transform Monday Night Raw and Friday Night SmackDown into high-voltage, stadium-lit live event megathreads with interactive match cards, crowd predictions, and native Reddit Live comments.**

Ultimate WWE Hub powers a streamlined 3-post ecosystem for wrestling communities on Reddit:

1. **WWE Belts, Stats & Upcoming Matches Hub**: Pinned community anchor showcasing official WWE championship belts, superstar win/loss analytics, and an editable upcoming show schedule.
2. **WWE Monday Night Raw Live Megathread**: Crimson-neon live event megathread deployed on Monday nights with `suggestedCommentSort: 'LIVE'`, live match cards, crowd chant reactions, and community predictions.
3. **WWE Friday Night SmackDown Live Megathread**: Electric-blue live event megathread deployed on Friday nights with `suggestedCommentSort: 'LIVE'`, live match cards, crowd chant reactions, and community predictions.

---

## Key Highlights

- **Streamlined 3-Post Architecture**: 3 dedicated custom post types provisioned directly from the subreddit moderator menu (`...`).
- **Live Megathread Scoreboard Strip**: Horizontal match card strip displaying all scheduled matchups, real-time match state tags, and instant match switching directly on the status card.
- **Native Live Comments**: Created with `suggestedCommentSort: 'LIVE'`, keeping newest fan comments at the top throughout the broadcast while the interactive card manages live match state.
- **Before vs. During vs. Finished Lifecycle**:
  - *Before Match*: Contender Tale of the Tape with dynamic W-L records and current streaks, 1-tap pre-match winner predictions, user picks tracking badge, and crowd consensus bars.
  - *During Match*: "IN RING" live bell alert, persistent crowd prediction consensus, soundboard chant buttons, and real-time community star rating.
  - *Finished Match*: Golden victory banner with finish method, user pick outcome badge, full consensus breakdown (percentage and vote counts), post-match star rating, and "AND NEW CHAMPION!" alert.
- **Titan-Tron Live Arena Ticker**: Rolling real-time headlines broadcasting match state changes, fan chant waves, and winner declarations.
- **Match-of-the-Night (MOTN) Honors**: Real-time crowd star ratings crown standout matches with high-contrast MOTN badges.
- **Post-Show Box Score & Trophy Case**: Inline feed card transforms into an official post-show recap upon event completion, and features a metallic Championship Trophy Case on Hub posts.
- **Moderator Live Studio & Hub Curator Suite**: In-arena match card customizer, belt selection, autocomplete superstar picks, stipulation quick-pills, match reordering (`[ MOVE UP ]` / `[ MOVE DOWN ]`), match deletion, schedule bulk import, event reopening, and dedicated Hub Curator trays to manage championship reigns, superstar stats, and upcoming PLE cards.
- **Realtime Transport**: Powered by Devvit realtime broadcast channels paired with authoritative Redis state.

---

## How It Works

### The 3-Step Lifecycle

1. **Deployment**: On Monday or Friday afternoon, a moderator selects **Create Monday Night Raw Live Megathread** or **Create Friday Night SmackDown Live Megathread** from the subreddit menu.
2. **Pre-Show Build-Up**: Before the opening bell, community members make their picks on the match card and view live consensus meters and contestant records.
3. **Showtime**: When the show begins, moderators click `[ START MATCH ]`. Fans trigger crowd chant reactions, rate match quality, follow real-time results on the scoreboard strip, and discuss the show in Reddit's native Live comment stream!

---

## Quick Setup (60-Second Onboarding)

1. **Install**: Add **Ultimate WWE Hub** to your subreddit via the Reddit Developer portal.
2. **Launch Anchor Hub**: From your subreddit menu (`...`), select **Create WWE Belts & Stats Hub Post** and pin it as a community anchor.
3. **Deploy Live Megathread**: On broadcast night, select **Create Monday Night Raw Live Megathread** or **Create Friday Night SmackDown Live Megathread**.
4. **Run the Show**: Use the moderator console to start matches, reorder the card, and declare winners as the action unfolds!

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
