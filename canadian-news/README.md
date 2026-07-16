# Canadian News App

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![News](https://img.shields.io/badge/Category-Regional_News-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Content_Curation-8A2BE2?style=for-the-badge)

**Canadian News App** is a premier moderator-controlled tool designed to deliver highly curated news from across Canada directly to your subreddit. It specifically prioritizes under-represented regions and specific topics to ensure a truly national, balanced perspective for community content.

## Key Features

- **On-Demand Execution**: Operates strictly under moderator control. The app will never automatically post without explicit manual initiation, allowing you to control the flow of information.
- **Dynamic Regional Balancing**: Employs an intelligent aggregation algorithm that ensures news is drawn from diverse areas across the country, preventing major metropolitan hubs from dominating the feed.
- **Configurable Subjects**: Tailor the news feed to your subreddit's interests by selecting specific news categories such as Politics, Health, Science, or Local Events.
- **Clean Rendering**: Automatically parses and formats article titles to ensure every submitted post is highly readable, professional, and free of clickbait clutter.

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/canadian-news-flowchart.png)

1. A moderator opens the subreddit's Mod Menu and selects the **Run News Fetcher** action.
2. The app aggregates the latest news from authorized Canadian sources based on your configured subject filters.
3. The stories are passed through the regional engine to ensure a balanced geographical distribution.
4. The approved stories are formatted into clean, readable posts and submitted to the subreddit.

## Setup & Configuration

1. **Install**: Add **Canadian News App** to your subreddit via the App Directory.
2. **App Settings**: Navigate to your subreddit's Mod Tools > App Settings > Canadian News App.
3. **Configure**:
   - Set your preferred batch size (number of articles to fetch per run).
   - Select the specific news categories (e.g., Politics, Health) you want to include.
4. **Usage**: Use the native subreddit Mod Menu action "Run News Fetcher" to initiate a post.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/canadian-news/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/canadian-news/PRIVACY.md)

---
*Built for Reddit's moderator community.*
