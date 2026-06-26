# DistroFeed Bot

A specialized Reddit automation tool that monitors distribution update feeds and automatically shares them with your community. Designed for Linux and software distribution subreddits, it ensures your users are always informed about the latest releases.

## Features

- **RSS Polling**: Automatically checks configured distribution feeds at regular intervals.
- **Smart Filtering**: Ensures only relevant updates are posted, preventing duplicates and spam.
- **GMT-4 Timezone Enforcement**: Precisely tracks "same-day" releases using a standardized timezone to maintain content freshness.
- **Clean Content**: Automatically decodes HTML entities in titles (e.g., converting `&amp;` to `&`) for a professional appearance.
- **Automated Posting**: Streamlines the submission process for moderators.

## Configuration

Settings can be managed directly through the Reddit Mod Tools menu:

| Setting | Description |
|---------|-------------|
| **Feed URL** | The RSS or Atom feed to monitor. |
| **Post Flair** | Automatically apply specific flair to release posts. |
| **Check Frequency** | How often to poll the feed for updates. |

## Technical Details

- **Language**: TypeScript
- **Platform**: Reddit Developer Platform (Devvit)
- **Version**: 0.12.19

---
*Built for the Reddit community.*
