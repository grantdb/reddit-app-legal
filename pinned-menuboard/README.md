> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/pinned-menuboard)

# Pinned Menuboard

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Hardened-red?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Subreddit_Utility-blueviolet?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Community_Styling-8A2BE2?style=for-the-badge)

> **Overcome Reddit's 2-pin limit with an interactive, visual 6-slot community showcase.**

Pinned Menuboard gives your subreddit a stylish navigation hub and game launcher. By creating a persistent 3x2 grid of featured threads, announcements, or mini-games, moderators can spotlight up to six posts simultaneously with single-tap post menu toggles.

---

## At a Glance

- **Bypass the 2-pin limit**: Feature up to six important community posts, wikis, or games at once.
- **Visual 3x2 card grid**: Showcase titles, authors, and high-resolution thumbnail preview cards.
- **One-tap menu toggling**: Add or remove featured posts directly from Reddit post overflow menus.
- **Dynamic board refresh**: The pinned hub updates automatically whenever featured items change.
- **Customizable branding**: Personalize header titles, community badges, and card styles.

---

## The Old Way vs. The Pinned Menuboard Way

| Traditional Workflow | With Pinned Menuboard |
| :--- | :--- |
| Constantly swapping and sacrificing one of your two pinned posts | **Permanent 6-slot interactive hub** featuring multiple events at once |
| Text-only link megathreads that nobody clicks | **Visual interactive card gallery** with rich thumbnails and direct links |
| Manually editing post markdown whenever a link changes | **One-tap post menu toggle** adding or removing items instantly |
| Forgetting to remove outdated event pins | **Centralized slot management** showing current featured occupancy |
| Cluttered sidebar link tables that get ignored on mobile | **Mobile-friendly custom post** rendering cleanly across all devices |

---

## Built for Rich Community Navigation

- **Interactive 3x2 Showcase Grid**: Displays up to six active cards featuring thumbnails, submission titles, and author attribution.
- **Post-Level Menu Actions**: Toggle any post onto the menuboard instantly by selecting **Toggle on Menuboard** in the post mod menu.
- **Automatic Thumbnail Resolution**: Pulls thumbnail images and media previews directly from Reddit submission payloads.
- **Zero-Friction Board Generation**: Spawn your master menuboard post with one click via **Generate Pinned Menuboard** in Mod Tools.
- **Slot Capacity Management**: Automatically validates available card slots and notifies moderators when the board is full.
- **Custom Theming & Text**: Adjust display titles and community greeting copy easily in App Settings.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/pinned-menuboard-flowchart.png)

### Your Four-Step Workflow

1. **Create**: A moderator clicks **Generate Pinned Menuboard** from Subreddit Mod Tools to create the master hub.
2. **Pin**: Sticky the generated Menuboard post to the top of your subreddit.
3. **Toggle**: When you find a quality post or interactive game to feature, click **Toggle on Menuboard** on that post.
4. **Refresh**: The master Menuboard post updates its interactive grid immediately for all community visitors.

---

## Quick Setup

1. **Install**: Add **Pinned Menuboard** to your subreddit through the Reddit App Directory.
2. **Generate Board**: Select **Generate Pinned Menuboard** from Subreddit Mod Tools and sticky the resulting post.
3. **Feature Content**: Open any post and select **Toggle on Menuboard** to add it to an open slot.
4. **Customize**: Adjust board headers and styling preferences in App Settings anytime.

*No markdown link tables to update manually. Visual community navigation directly inside your feed.*

---

## Advanced Capabilities

Pinned Menuboard is engineered for dynamic Custom Post rendering and fast slot index updates.

- **Interactive Webview Grid**: Built with responsive HTML5/CSS grid layouts optimized for mobile and desktop screens.
- **Media Asset Resolver**: Automatically fetches and optimizes preview assets via Reddit's native media proxy.
- **Redis Slot Indexing**: Stores active card IDs and metadata in Redis hashes with atomic occupancy controls.
- **Menu Action Handlers**: Registers dedicated endpoint handlers (`/internal/menu/post-toggle`) for rapid mod toggles.

---

## Designed to Assist Moderators

Pinned Menuboard provides visual post curation and navigation tools to enhance community engagement. Featured posts are selected and managed exclusively by your moderation team—human moderators maintain full control over which posts are showcased or removed.

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
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/pinned-menuboard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/pinned-menuboard/PRIVACY.md)

---
*Built for Reddit's moderator community.*
