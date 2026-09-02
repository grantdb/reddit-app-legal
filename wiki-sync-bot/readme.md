> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/wiki-sync-bot)

# WikiSync Bot

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Utility-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Wiki_Engine-8A2BE2?style=for-the-badge)

> **Automated, reliable subreddit wiki synchronization and documentation management for Reddit.**

WikiSync Bot provides subreddit moderators with a high-reliability engine to publish, manage, and synchronize wiki documentation and support schemas directly within Reddit. Dual-writes across modern (v2) and legacy (v1) Reddit wiki stores to eliminate rich-text corruption and keep community knowledge up to date.

---

## At a Glance

- **Dual-Version Subreddit Wiki Writes**: Direct programmatic synchronization to both modern (`v2`) and legacy (`v1`) Reddit wiki endpoints.
- **Support Schema Synchronization**: Automatically deploys `bot_knowledge` JSON payloads to `r/grantdb/wiki/bot_knowledge` bypassing rich-text quote mangling.
- **Fleet Documentation Sync**: Incremental background hash comparison and synchronization across all fleet application documentation pages.
- **Automated Release Announcements**: Automatically detects new app releases and publishes structured update threads with changelog notes and wiki guides directly to **r/grantdb**.
- **Unified Moderator Menu Popout**: Open **WikiSync Bot** from the subreddit overflow menu (`...`) to run incremental syncs, single-app updates, full re-syncs, schema deployments, or broadcast immediate app release announcements.
- **Moderator-Restricted Controls**: Built-in permissions ensuring only authorized community moderators can trigger wiki sync operations.

---

## The Old Way vs. The WikiSync Bot Way

| Traditional Workflow | With WikiSync Bot |
| :--- | :--- |
| Manually copying and pasting documentation across multiple subreddit wiki pages | **Automated background synchronization** comparing SHA-256 hashes and updating changed pages |
| Rich-text editors corrupting JSON quotes into curly quotes | **Direct API dual-writes (v2 + v1)** preserving raw formatting perfectly |
| Forgetting to post release announcements on r/grantdb | **Automated release broadcast engine** publishing changelogs directly to r/grantdb |
| Complex custom OAuth2 wiki scripts on external VPS servers | **Native Devvit architecture** operating securely inside Reddit infrastructure |
| Missing audit trails for wiki revisions | **Structured revision reasons** logged with every page creation and update |

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/wiki-sync-bot-flowchart.png)

### Your Four-Step Workflow

1. **Install & Schedule**: WikiSync Bot automatically schedules a recurring 15-minute background sync and configures test targets in Mod Tools > App Settings.
2. **Sync Manifest**: WikiSync Bot checks the remote fleet manifest (`wiki-manifest.json`) and release manifest (`releases/manifest.json`).
3. **Dual-Write & Broadcast Engine**: Fetches clean HTML/JSON payloads from GitHub, writes directly to Reddit wiki endpoints, and posts release announcements for newly shipped versions.
4. **Live Verification & Deduplication**: Reads back and verifies the updated wiki page revisions and caches announcement IDs in Redis to guarantee zero duplicate posts.

---

## Quick Setup

1. **Install**: Add **WikiSync Bot** to your subreddit.
2. **Configure**: Open **Mod Tools > App Settings > WikiSync Bot** to toggle wiki sync and release announcements.
3. **Trigger Operations**: Open the subreddit menu (`...`), select **WikiSync Bot**, and choose your action:
   - **Sync Changed Wiki Pages**: Check manifest and update modified app pages incrementally.
   - **Sync Single App Wiki**: Fetch and update a specific app's documentation page.
   - **Force Sync All Wiki Pages**: Full re-synchronization of all fleet wiki pages in the background.
   - **Sync Bot Knowledge Schema**: Update `bot_knowledge` JSON schema directly.
   - **Broadcast App Release Announcement**: Immediately publish or re-publish an update announcement post for any fleet app.

---

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

---

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/wiki-sync-bot/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/wiki-sync-bot/PRIVACY.md)

---
*Built for Reddit's moderator community.*
