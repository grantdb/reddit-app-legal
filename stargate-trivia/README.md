> **User Guide & Overview** | [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/stargate-trivia)

# Stargate Trivia

> **Challenge your community with curated Stargate trivia rounds and persistent live leaderboards directly inside Reddit posts.**

**Stargate Trivia** is an interactive engagement game built on Reddit Devvit. Moderators launch a custom trivia post from the subreddit menu, and players jump into a 10-question gauntlet with real-time scoring and persistent Redis leaderboards on mobile and desktop.

---

## At a Glance

- **Curated Franchise Library**: Deep pool of canonical Stargate trivia questions tailored for casual fans and lore experts alike.
- **Persistent Live Leaderboards**: Tracks personal bests and top subreddit scores directly on each event post via Redis.
- **Dual-Mode Responsive UI**: Clean inline feed card that launches smoothly into expanded gameplay on both mobile and desktop.
- **Zero Ongoing Maintenance**: Automatically validates answers, calculates scores, and updates rankings with no moderator upkeep.

---

## How It Works: The 4-Step Operational Pipeline

### 01 · Launch Event Post

> **One-click moderator deployment**
> - A moderator opens the subreddit menu (`...`) and selects **Create Stargate Trivia Post**.
> - The app publishes an interactive custom post into the subreddit feed.

---

### 02 · Enter Expanded Gameplay

> **Seamless inline-to-expanded transition**
> - Players tap the inline trivia card to open the full-screen 10-question trivia gauntlet.
> - Navigation and back-button handling keep players cleanly inside the Reddit experience.

---

### 03 · Answer & Score

> **Real-time validation and scoring**
> - Each correct answer awards points (+100 per question) with instant feedback.
> - Session state and scoring run autonomously on the Devvit Web backend.

---

### 04 · Save High Scores

> **Persistent Redis leaderboard updates**
> - Completed rounds verify and save the player's highest score to the post's live leaderboard.
> - Players can review final rankings or jump into another round immediately.

---

## Quick Setup

1. **Install**: Add **Stargate Trivia** to your subreddit via the Reddit App Directory.
2. **Launch**: Open the subreddit menu (`...`) and select **Create Stargate Trivia Post**.
3. **Play**: Community members tap the post to play and compete on the persistent leaderboard with zero ongoing moderation required.

---

## Support

> **Community Support & Feature Requests**
> For questions, troubleshooting, or bug reports, join the official community:
> **[https://www.reddit.com/r/grantdb](https://www.reddit.com/r/grantdb)**

- **User Guide**: [https://www.reddit.com/r/grantdb/wiki/stargate-trivia/](https://www.reddit.com/r/grantdb/wiki/stargate-trivia/)
- **Technical Reference**: [https://www.reddit.com/r/grantdb/wiki/index/all-apps/stargate-trivia/](https://www.reddit.com/r/grantdb/wiki/index/all-apps/stargate-trivia/)

---

## Legal

- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/stargate-trivia/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/stargate-trivia/PRIVACY.md)

---
*Built for fun on Reddit*
