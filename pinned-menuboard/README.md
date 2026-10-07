> **User Guide & Overview** | [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/pinned-menuboard)

# Pinned Menuboard

> **Overcome Reddit's 2-pin limit with an interactive, visual showcase featuring high-resolution previews, customizable themes, and in-webview moderator controls.**

Pinned Menuboard gives your subreddit a stylish navigation hub and game launcher. By creating a persistent showcase of featured threads, announcements, or community resources, moderators can spotlight up to twelve posts simultaneously with single-tap post menu toggles or direct in-webview management.

---

## At a Glance

- **Bypass the 2-pin limit**: Feature from two to twelve community threads, wikis, or games simultaneously in a clean card grid.
- **Rich thumbnails & fallback graphics**: Automatically extracts high-resolution artwork from Reddit posts, rich previews, gallery items, and markdown body links, with dynamic glassmorphic vector presets and custom URL overrides.
- **Dark and Light themes**: Toggle between Dark Mode (light on dark) and Light Mode (dark on light) with a single click.
- **Community Highlights auto-unpin**: Automatically unpins posts from Reddit's native Community Highlights when featured, eliminating duplicate feed cards.
- **In-webview moderator controls**: Customize board headers, adjust capacity, and reorder or remove cards directly inside the post.
- **One-tap menu toggling**: Feature or remove posts instantly from the native Reddit post overflow menu.

---

## Built for Rich Community Navigation

- **Dynamic Showcase Grid**: Displays 2 to 12 responsive cards featuring high-impact image previews, submission titles, and author attribution.
- **Multi-Tier Thumbnail Resolution**: Resolves high-resolution thumbnails via Devvit enriched image APIs, standard post thumbnails, direct image links, and preview payloads.
- **Dedicated Moderator Controls**: Subreddit moderators receive an in-post Customize button granting access to live configuration without leaving the thread.
- **Theme Selection**: Switch between Dark Mode (light on dark slate `#0b1426`) and Light Mode (dark on clean light `#f8fafc`).
- **Capacity Controls**: Configure slot limits (2, 4, 6, 8, 10, or 12 cards) with automatic capacity validation.
- **Community Highlights Integration**: Automatically unpins stickied posts when featured so they do not duplicate inside Reddit's native top highlights bar.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/pinned-menuboard-flowchart.png)

### Your Four-Step Workflow

1. **Generate**: A moderator clicks **Generate Pinned Menuboard** from Subreddit Mod Tools to create the master custom post.
2. **Sticky**: The custom post is stickied to the top of your subreddit feed.
3. **Feature & Unpin**: Open any post and click **Toggle on Menuboard** (or paste the post URL into the Customize panel). The post is added to the board and automatically unpinned from Community Highlights.
4. **Customize**: Click **Customize** in the board header to adjust themes, change the board title, adjust slot capacity, or reorder active cards.

---

## Quick Setup

1. **Install**: Add **Pinned Menuboard** to your subreddit through the Reddit App Directory.
2. **Generate Board**: Select **Generate Pinned Menuboard** from Subreddit Mod Tools.
3. **Feature Threads**: Open any post menu (`...`) and click **Toggle on Menuboard**, or use the in-webview **Customize** panel.
4. **Tune Settings**: Click **Customize** in the top-right corner of the board to set your preferred theme, title, and slot count.

---

## Advanced Capabilities

Pinned Menuboard is engineered with Devvit Webview architecture for real-time reactivity and lightweight Redis storage.

- **Atomic Redis Concurrency**: Updates use distributed Redis locking to ensure thread-safe capacity and reordering operations.
- **Automated Thumbnail Backfill**: Automatically inspects existing featured items and enriches them with high-resolution artwork upon initialization.
- **Moderator-Gated Endpoints**: Dedicated API endpoints (`/api/settings`, `/api/manage-post`) enforce strict moderator permission checks before modifying community configuration.
- **Zero-Poll Webview**: Fast client initialization with instant optimistic updates and DOM synchronization.

---

## Designed to Assist Moderators

Pinned Menuboard provides visual post curation and navigation tools to enhance community engagement. Featured posts are selected and managed exclusively by your moderation team—human moderators maintain full authority over all showcased content.

---

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

## Legal

This application is subject to the following legal agreements:

- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/pinned-menuboard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/pinned-menuboard/PRIVACY.md)

---
*Built for Reddit's moderator community.*
