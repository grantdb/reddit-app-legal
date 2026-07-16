# GuardHub: Format Guard 🛡️

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Content_Policy-8A2BE2?style=for-the-badge)

**Format Guard** is a highly focused moderation app designed to enforce strict structure and title-shape rules within your community. By ensuring that all submissions adhere to specific stylistic standards, it prevents low-effort formatting, ALL-CAPS screaming, and clickbait structures from cluttering the subreddit.

## Key Features

- **Structural Constraints**: Strictly enforce minimum and maximum character lengths for both titles and body text to prevent single-word spam or unreadable walls of text.
- **Stylistic Case Control**: Automatically detect and prevent all-caps titles, excessive uppercase text, or alternating-case troll posts.
- **Punctuation Abuse**: Intercept and reject submissions containing repeated punctuation strings (e.g., "Help!!!!???").
- **Prefix/Suffix Tags**: Require mandatory text tags in titles (e.g., `[Request]`, `[Spoilers]`) to ensure submissions are categorized cleanly before they even reach the feed.
- **Private Dashboard**: Complete with a fully secure, moderator-only control panel for managing formatting rules without writing complex Regex.

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/format-guard-flowchart.png)

1. A user attempts to submit a new post to the community.
2. Format Guard intercepts the post and runs the text through your active formatting rules sequentially.
3. If any rule is violated, the post is instantly removed, and the user receives an automated message explaining exactly which formatting rule they broke, allowing them to correct and resubmit.

## Setup & Configuration

1. **Install**: Add **Format Guard** to your subreddit via the App Directory.
2. **Dashboard Initialization**: Navigate to your subreddit's Mod Tools and open the GuardHub: Format Guard Dashboard.
3. **Configure Rules**: 
   - Navigate to the Rules tab to create your first structural constraint (e.g., "Title must contain [Tag]").
   - We highly recommend using the built-in Test tab to verify your rule logic before enforcing it live.
4. **Monitoring**: Review formatting rejections in the Dashboard logs to adjust rule sensitivity over time.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/format-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/format-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
