> **User Guide & Overview** | [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/wiki-sync-bot)

# WikiSync Bot

> **Automated subreddit wiki synchronization, `bot_knowledge` schema deployment, and release announcements for `r/grantdb`.**

WikiSync Bot provides subreddit moderators with a high-reliability engine to publish, manage, and synchronize wiki documentation and support schemas directly within Reddit. It dual-writes across modern (`v2`) and legacy (`v1`) Reddit wiki stores and posts public app release announcements to `r/grantdb`.

> **Documentation**: [Full User Guide](https://www.reddit.com/r/grantdb/wiki/wiki-sync-bot/) | [Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/wiki-sync-bot/)

---

## At a Glance

- **Dual-Version Subreddit Wiki Writes**: Synchronizes documentation to both modern (`v2`) and legacy (`v1`) Reddit wiki endpoints.
- **Support Schema Synchronization**: Deploys `fleet-knowledge.bot.json` to `r/grantdb/wiki/bot_knowledge` for `reference-reply-bot`.
- **Incremental & Locked Fleet Sync**: Compares `wiki-manifest.json` hashes in Redis, uses a Redis run mutex to prevent overlapping syncs, and batches updates safely.
- **Automated Release Announcements**: Detects newly shipped public apps from `releases/manifest.json` and posts formatted update threads to `r/grantdb` with Redis deduplication.

---

## How It Works: The 4-Step Operational Pipeline

### 01 · Install & Schedule
> **Initialize recurring background syncs**
> - On `AppInstall` and `AppUpgrade`, cancels stale `wiki_sync_poll` jobs and schedules a recurring 15-minute cron plus an initial 5-second sync.

---

### 02 · Fetch Remote Manifests
> **Check for documentation and release updates**
> - Fetches `wiki-manifest.json` and `releases/manifest.json` from `raw.githubusercontent.com` using bounded 10-second timeouts and strict slug validation.

---

### 03 · Dual-Write & Broadcast Engine
> **Publish wiki pages and public release threads**
> - Strips `shields.io` badges and writes `index/all-apps/<slug>` and `<slug>` to both `v2` and `v1` wiki stores in bounded batches.
> - Posts release announcements for newly shipped public apps when `enable_release_announcements` is enabled.

---

### 04 · Verification & Deduplication
> **Prevent stale caches and duplicate announcements**
> - Caches manifest hashes in Redis only after at least one wiki write succeeds, performs live `v2` read-back verification on single-app syncs, and tracks posted announcement versions in Redis.

---

## Quick Setup

1. **Install**: Add **WikiSync Bot** to your subreddit.
2. **Configure**: Open **Mod Tools > App Settings > WikiSync Bot** to toggle `enable_release_announcements`.
3. **Trigger Operations**: Open the subreddit `...` menu, select **WikiSync Bot**, and run incremental sync, single-app sync, force sync, `bot_knowledge` sync, or manual release broadcast.

---

## Support

> **Community Support & Feature Requests**
> For questions, troubleshooting, or bug reports, join the official community:
> **[https://www.reddit.com/r/grantdb](https://www.reddit.com/r/grantdb)**

- **User Guide**: [https://www.reddit.com/r/grantdb/wiki/wiki-sync-bot/](https://www.reddit.com/r/grantdb/wiki/wiki-sync-bot/)
- **Technical Reference**: [https://www.reddit.com/r/grantdb/wiki/index/all-apps/wiki-sync-bot/](https://www.reddit.com/r/grantdb/wiki/index/all-apps/wiki-sync-bot/)

---

## Legal

- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/wiki-sync-bot/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/wiki-sync-bot/PRIVACY.md)

---
*Built for Reddit's moderator community.*
