> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/archive-guard)

# Archive-Guard 🛡️

![Reddit](https://img.shields.io/badge/Platform-Reddit%20Devvit-FF4500?style=flat-square)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=flat-square)

> *Subreddit memory without the repetition.*

Stop answering the exact same recurring questions every week. **Archive-Guard** is a lightweight, zero-bloat Devvit moderation tool that indexes discussion topics, clusters repeat questions, and points community members directly to your subreddit's definitive canonical threads.

---

## Purpose

Subreddits frequently suffer from repeat questions (*"Best beginner setup?"*, *"How to fix error code 404?"*, *"Where do I start?"*). Moderators spend excessive energy either re-explaining answers or hunting down old links. Archive-Guard maintains an explainable topic memory, giving moderators 1-click tools to anchor discussions to canonical guides and review community topic leaderboards.

---

## Major Features

- **Explainable Topic Clustering**: Automatically extracts meaningful tokens and bigrams to detect recurring discussion subjects on post submission without black-box magic.
- **Unified Post Menu Popout**: Open **Archive-Guard** on any post to designate canonical guides, view topic history, or exempt false positives.
- **Mod-Safe by Design**: Operates purely as a moderator assistant with private mod reports and internal logs. No automatic post removals or intrusive user interruptions in v1.
- **On-Demand Community Digests**: Generate clean markdown summaries spotlighting your most frequently discussed topics and essential resources.
- **Atomic Redis Reliability**: Powered by Redis transactions and strict single-trigger idempotency for exact-once execution.

---

## Workflow & Logic

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/archive-guard-flowchart.png)

---

## Moderator Actions

### Post Overflow Menu Popout
Open the post menu (`...`) and click **Archive-Guard** to access:
- **Set as Canonical Guide**: Designates the post as the master reference thread for this topic cluster.
- **View Topic History**: Displays topic volume, matching keywords, and past related submissions.
- **Ignore Match**: Exempts false positives so the post will not trigger repeat alerts.

### Subreddit Overflow Menu
- **Archive-Guard: Generate Digest**: Compiles a markdown leaderboard digest of top recurring topics and canonical guides for moderator review.

---

## Install / Use

1. Install **Archive-Guard** on your subreddit through the Reddit App Directory.
2. The app automatically listens to new submissions via `onPostSubmit`.
3. Use the post **Archive-Guard** popout to manage canonical threads as high-quality guides appear.
4. Use the subreddit menu to generate a topic digest at any time.

---

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

---

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/archive-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/archive-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
