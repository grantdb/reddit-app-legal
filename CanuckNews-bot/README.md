# Canuck News Bot

A moderator-controlled news tool designed to deliver curated, non-political news from across Canada with a focus on balanced regional representation. This bot allows moderators to manually trigger news updates, ensuring every part of the country is heard while maintaining a neutral, high-quality content standard.

## Features

- **Manual Trigger**: Operates only when manually triggered by a moderator via the "Run News Fetcher" menu item.
- **Adjustable Batch Size**: Configurable "Posts per Run" setting to control exactly how many items are posted at once.
- **Regional Balancing**: Prioritizes news from regions with lower coverage to ensure diverse national representation.
- **Content Filtering**: Automatically identifies and filters out political content to keep the subreddit focused on general news and community interests.
- **HTML Cleanup**: Decodes HTML entities in titles for clean, readable headlines.
- **Timezone Precision**: Uses GMT-4 (Eastern Time) for consistent "same-day" content filtering.

## Configuration & Domains

The bot securely fetches data from the following trusted sources:
- `cbc.ca` (Regional news coverage)
- `globalnews.ca` (Science and technology)
- `theglobeandmail.com` (Business and national updates)

## Technical Architecture

- **Redis Integration**: Robust deduplication and regional post-count tracking.
- **Reddit API**: Seamless moderator-initiated submissions.
- **TypeScript & Devvit**: Built on version 0.12.19 for maximum reliability.

---
*Built for the Reddit community.*
