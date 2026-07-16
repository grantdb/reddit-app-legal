# GuardHub: Comment Guard 🛡️

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Automoderator-8A2BE2?style=for-the-badge)

**Comment Guard** is a specialized moderation engine designed to identify and penalize low-effort requests while preserving constructive, helpful discussion. It uses a nuanced weighted scoring system to distinguish between spammy, repetitive demands and genuine feedback, ensuring your community maintains high quality discourse.

## Key Features

- **Weighted Scoring System**: Unlike simple keyword matching, Comment Guard penalizes short, repetitive phrases (e.g., "pls fix", "update when") while granting score offsets for constructive signals (e.g., length, punctuation, context).
- **Dynamic Action Reasons**: When a comment is removed, the app generates a detailed report reason that includes the specific score and the exact patterns that triggered the penalty, giving moderators clear context.
- **Safety Guards**: Automatically exempts AutoModerator, other bots, and authenticated moderators from being penalized, preventing accidental friendly-fire.
- **Private Dashboard**: Features a fully secure, moderator-only control panel for adjusting threshold sensitivities and reviewing enforcement logs.

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/comment-guard-flowchart.png)

1. A user submits a new comment in the subreddit.
2. Comment Guard catches the event and verifies the author is not a moderator or exempt bot.
3. The comment text is analyzed against a dictionary of low-effort patterns and constructive markers to calculate a final penalty score.
4. If the score exceeds your configured threshold, the comment is removed and a detailed report is attached for moderator review.

## Setup & Configuration

1. **Install**: Add **Comment Guard** to your subreddit via the App Directory.
2. **Dashboard Initialization**: Navigate to your subreddit's Mod Tools and open the GuardHub: CommentGuard Dashboard.
3. **Configure Thresholds**: Use the interactive interface to set how sensitive the scoring system should be (e.g., what score triggers a removal).
4. **Monitoring**: The app operates silently in the background. You can review all enforcement actions and their exact scoring breakdowns via the Dashboard logs.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/comment-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/comment-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
