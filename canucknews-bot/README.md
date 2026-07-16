# Canuck News Bot

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-News-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Content_Curation-8A2BE2?style=for-the-badge)

**Canuck News Bot** is a moderator-controlled tool designed to deliver curated, balanced, and non-political news from across Canada directly to your subreddit. By strictly enforcing neutral, high-quality standards, it allows communities to stay informed without introducing controversial or biased political content.

## Key Features

- **On-Demand Execution**: The bot operates strictly under moderator control and does not auto-post without consent. You decide when the news is shared.
- **Regional Balancing**: Intelligently curates stories to prioritize news from under-represented Canadian regions, ensuring a geographically balanced feed.
- **Content Filtering**: Automatically scans and filters out political content or highly controversial subjects to keep community discourse neutral.
- **Clean Rendering**: Ensures all article titles are properly formatted, readable, and free of clickbait artifacts.

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/CanuckNews-bot-flowchart.png)

1. A moderator opens the Mod Menu and clicks the **Run News Fetcher** action.
2. The app aggregates the latest news from a predefined list of Canadian sources.
3. The content goes through the regional balancer and political filter.
4. The approved stories are formatted into a clean, readable post and submitted to the subreddit.

## Setup & Configuration

1. **Install**: Add **Canuck News Bot** to your subreddit via the App Directory.
2. **App Settings**: Navigate to your subreddit's Mod Tools > App Settings > Canuck News Bot.
3. **Configure**:
   - Set your preferred batch size (number of articles per post).
   - Toggle specific regional priorities if your subreddit focuses on a specific province.
4. **Usage**: Use the native subreddit Mod Menu action "Run News Fetcher" to generate a post.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/CanuckNews-bot/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/CanuckNews-bot/PRIVACY.md)

---
*Built for Reddit's moderator community.*
