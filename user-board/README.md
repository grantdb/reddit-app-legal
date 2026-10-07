> **User Guide & Overview** | [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/user-board)

# User Board

> **Gamify community engagement and showcase your top contributors in a live, quality-driven leaderboard.**

User Board recognizes and rewards your most valuable community members. Calculating participation scores based on community reception (post upvotes, comment upvotes, and discussion threads) rather than raw post volume, it renders a visual, interactive leaderboard post directly inside your subreddit to encourage constructive participation.

---

## At a Glance

- **Interactive visual leaderboard**: Display top community contributors in a rich, responsive custom post.
- **Engagement-first scoring**: Rewards positive community reception (upvotes on posts & comments) and discussion depth rather than spammy post volume.
- **Full comment ingestion**: Evaluates top commenters, comment upvote scores, and reply threads alongside post authors.
- **Customizable scoring weights**: Fine-tune independent multipliers for post upvotes, comment upvotes, discussion sparked, and baseline counts.
- **Automated rank calculations**: Scheduled background jobs keep rankings fresh without manual tallying.
- **Moderator customization console**: Tune score formulas, tier cutoffs, and timeframes from the inline **⚙ Settings** console.
- **Mobile-friendly custom post**: Fast, client-side rendered experience that loads smoothly on all platforms.

---

## Built for Vibrant Community Growth

- **Nuanced Engagement Scoring**: Configure independent point multipliers for post upvotes (3x default), comment upvotes (2x default), comments on posts (2x default), and thread replies (1x default).
- **Quality-First Anti-Spam Design**: Downvoted submissions receive zero upvote points, preventing spammers from gaming the board through volume alone.
- **Rich Contributor Badges**: Classifies contributors into recognizable community roles (*Top Poster*, *Commenter*, *Engager*, *Consistent*, and *Rising Star*).
- **Interactive React Custom Post**: Features rich leaderboard views with user rank badges, avatars, and historical score milestones.
- **Automated Rank Refreshes**: Scheduled background workers re-calculate scores and update cached rankings automatically.
- **Zero-Friction Board Generation**: Deploy your leaderboard post with one click using **Create Subreddit User Board** in Subreddit Mod Tools.
- **Moderator Tuning Console**: Adjust point weights, calculation time horizons, and exclusion rules easily from the inline **⚙ Settings** button.
- **Privacy-Safe Data Hygiene**: Aggregates public subreddit statistics into anonymous Redis score counters without collecting personal data.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/user-board-flowchart.png)

### Your Four-Step Workflow

1. **Deploy**: A moderator selects **Create Subreddit User Board** from Subreddit Mod Tools to spawn the interactive hub.
2. **Collect**: Background tasks scan recent subreddit submissions and comment threads, indexing upvotes and reply depth.
3. **Calculate**: The engine evaluates activity stats against your custom point weights to generate contributor ranks based on positive reception.
4. **Render**: The pinned leaderboard post updates its interactive UI to display the latest top community contributors.

---

## Quick Setup

1. **Install**: Add **User Board** to your subreddit through the Reddit App Directory.
2. **Generate Post**: Select **Create Subreddit User Board** from Subreddit Mod Tools.
3. **Configure Weights**: Click **⚙ Settings** in the top-right corner of the generated post to adjust point multipliers and timeframes.
4. **Pin**: Sticky the generated post to your subreddit to start showcasing top contributors.

*No manual score tallying required. Automated community gamification directly inside Reddit.*

---

## Advanced Capabilities

User Board is engineered for fast score computation and lightweight Custom Post Webview rendering.

- **Weighted Score Pipeline**: Computes author scores using linear combination formulas (`points = w1*posts + w2*comments + w3*karma`).
- **Redis High-Performance Snapshot Caching**: Stores subreddit contributor rankings and active timeframe slices in Redis for sub-millisecond retrieval.
- **Inline Modal Architecture**: Renders full leaderboards and moderator consoles inline without intrusive full-page redirects.
- **Automated Ingestion Crons**: Runs scheduled background aggregation cycles to minimize client-side API overhead.

---

## Designed to Assist Moderators

User Board provides participation analytics and dynamic leaderboards to assist in community gamification and member recognition. Leaderboard rankings serve as engagement tools—human moderators maintain complete authority over point weights, rules, and community visibility.

---

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

## Legal

This application is subject to the following legal agreements:

- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/user-board/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/user-board/PRIVACY.md)

---
*Built for Reddit's moderator community.*
