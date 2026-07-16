# User Board

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Analytics-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Community_Engagement-8A2BE2?style=for-the-badge)

**User Board** is a robust analytics and engagement tool that identifies your top community contributors and dynamically renders a visually stunning, real-time leaderboard. By gamifying participation, it encourages high-quality submissions and rewards users who consistently add value to your subreddit.

## Key Features

- **High-Precision Scoring**: Move beyond simple upvote counting. User Board normalizes and computes author scores using custom weight configurations, allowing you to value comments differently than posts.
- **Lightning Fast**: Powered by efficient data aggregation, the interactive leaderboard loads instantly within the post without causing Reddit client delays.
- **Moderator Console**: Features a built-in control panel allowing moderators to easily configure custom weights, set level cutoffs, and adjust the calculation timing directly from the app.
- **Automated Updates**: Once deployed, the board automatically fetches the latest data on a schedule, keeping the community's ranks fresh without manual intervention.

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/user-board-flowchart.png)

1. A background job runs at a predefined interval to gather recent activity in the subreddit.
2. The engine fetches raw data for user posts, comments, and upvotes.
3. The raw data is passed through your custom scoring algorithm (e.g., Comments are worth 2x Posts).
4. The users are ranked, and the live leaderboard post is updated with the new standings.

## Setup & Configuration

1. **Install**: Add **User Board** to your subreddit via the App Directory.
2. **Dashboard Initialization**: Navigate to your subreddit's Mod Tools and open the User Board Dashboard.
3. **Configure Weights**: Use the interface to define how much weight posts, comments, and karma should have in the final score.
4. **Deploy**: Generate the leaderboard post via the Mod tools menu and pin it to the top of your subreddit for maximum visibility.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/user-board/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/user-board/PRIVACY.md)

---
*Built for Reddit's moderator community.*
