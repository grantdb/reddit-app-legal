> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/user-board)

# User Board

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Hardened-red?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Analytics-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Community_Engagement-8A2BE2?style=for-the-badge)

> **Gamify community engagement and showcase your top contributors in a live leaderboard.**

User Board recognizes and rewards your most valuable community members. Calculating participation scores based on custom post and comment weights, it renders a visual, interactive leaderboard post directly inside your subreddit to drive constructive discussion.

---

## At a Glance

- **Interactive visual leaderboard**: Display top community contributors in a rich, responsive custom post.
- **Customizable scoring weights**: Balance points awarded for posts, comments, upvotes, and discussion engagement.
- **Automated rank calculations**: Scheduled background jobs keep rankings fresh without manual tallying.
- **Moderator customization console**: Tune score formulas, tier cutoffs, and layout styles from App Settings.
- **Mobile-friendly custom post**: Fast, client-side rendered experience that loads smoothly on all platforms.

---

## The Old Way vs. The User Board Way

| Traditional Workflow | With User Board |
| :--- | :--- |
| Manually tracking and tallying top monthly posters in spreadsheets | **Automated background ranking** refreshing contributor scores on schedule |
| Generic karma counts that don't reflect true community helpfulness | **Custom weighted formula** valuing comments and discussion quality |
| Static text posts listing usernames that quickly go out of date | **Live interactive custom post** displaying dynamic ranks and badges |
| Forgetting to run monthly contributor reward posts | **Always-on leaderboard hub** pinned directly to your subreddit feed |
| No way for community members to track their standing | **Engaging visual scoreboard** motivating constructive participation |

---

## Built for Vibrant Community Growth

- **Nuanced Contribution Scoring**: Configure independent point multipliers for submission upvotes, comment volume, and discussion activity.
- **Interactive React Custom Post**: Features rich leaderboard views with user rank badges, avatars, and historical score milestones.
- **Automated Rank Refreshes**: Scheduled background workers re-calculate scores and update cached rankings automatically.
- **Zero-Friction Board Generation**: Deploy your leaderboard post with one click using **Create Subreddit User Board** in Subreddit Mod Tools.
- **Moderator Tuning Console**: Adjust point weights, calculation time horizons, and display tiers easily from App Settings.
- **Privacy-Safe Data Hygiene**: Aggregates public subreddit statistics into anonymous Redis score counters without collecting personal data.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/user-board-flowchart.png)

### Your Four-Step Workflow

1. **Deploy**: A moderator selects **Create Subreddit User Board** from Subreddit Mod Tools to spawn the interactive hub.
2. **Collect**: Background tasks scan recent subreddit activity, aggregating post scores and comment counts.
3. **Calculate**: The engine evaluates activity stats against your custom point weights to generate contributor ranks.
4. **Render**: The pinned leaderboard post updates its interactive UI to display the latest top community members.

---

## Quick Setup

1. **Install**: Add **User Board** to your subreddit through the Reddit App Directory.
2. **Configure Weights**: Open **Mod Tools > App Settings > User Board** to adjust point multipliers.
3. **Generate Post**: Select **Create Subreddit User Board** from Subreddit Mod Tools.
4. **Pin**: Sticky the generated post to your subreddit to start showcasing top contributors.

*No manual score tallying required. Automated community gamification directly inside Reddit.*

---

## Advanced Capabilities

User Board is engineered for fast score computation and lightweight Custom Post Webview rendering.

- **Weighted Score Pipeline**: Computes author scores using linear combination formulas (`points = w1*posts + w2*comments + w3*karma`).
- **Redis Sorted Set Ranking**: Stores member scores in high-performance Redis Sorted Sets (`ZSET`) for sub-millisecond rank lookups.
- **Multi-Entrypoint Webview**: Supports independent entrypoints for main feed cards, full leaderboards, and settings consoles.
- **Automated Ingestion Crons**: Runs scheduled background aggregation cycles to minimize client-side API overhead.

---

## Designed to Assist Moderators

User Board provides participation analytics and dynamic leaderboards to assist in community gamification and member recognition. Leaderboard rankings serve as engagement tools—human moderators maintain complete authority over point weights, rules, and community visibility.

---

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include:
- The app name.
- What you expected to happen.
- What happened instead.
- Any error message.
- Screenshots or relevant details.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/user-board/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/user-board/PRIVACY.md)

---
*Built for Reddit moderators.*
