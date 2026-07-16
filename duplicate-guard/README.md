# GuardHub: Duplicate Guard 🛡️

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Hardened-red?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blueviolet?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Spam_Control-8A2BE2?style=for-the-badge)

**Duplicate Guard** is an advanced subreddit moderation app designed to keep your community feed fresh by automatically identifying and mitigating repetitive subjects or topics. When a new post is submitted, it compares the title against recent community submissions to catch and remove reworded reposts and duplicate topics before they clutter your front page.

*Note: This app focuses on semantic text duplicates. For strict URL or domain matching, see Domain Guard.*

## Key Features

- **Configurable Match Modes**: Choose between strict exact-title matching or a more advanced algorithmic matching engine that detects slightly reworded titles covering the exact same subject.
- **Adjustable Time Windows**: Fully configure how many recent posts or how many days back the engine should look when checking for duplicates.
- **Fail-Safe Operation**: Built with strict "effectively-once" guarantees, ensuring that duplicate Reddit platform events or network retries will never result in duplicate moderation actions on users.
- **Granular Exemptions**: Easily configure the engine to ignore posts made by moderators, approved users, or posts tagged with specific flairs (like Mega-threads).

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/duplicate-guard-flowchart.png)

1. A new post event is received by Duplicate Guard.
2. The app verifies the author isn't exempt (e.g., a moderator).
3. It fetches the configured history window of recent posts and applies the selected text comparison algorithm (Strict or Balanced).
4. If a match exceeds the similarity threshold, the new post is removed as a duplicate topic.

## Setup & Configuration

1. **Install**: Add **Duplicate Guard** to your subreddit via the App Directory.
2. **App Settings**: Navigate to your subreddit's Mod Tools > App Settings > Duplicate Guard.
3. **Configure Settings**: 
   - Adjust the Match Mode (Strict, Balanced, or Aggressive).
   - Set the lookback window (e.g., check against the last 100 posts).
4. **Monitoring**: The app automatically runs in the background monitoring new posts without further interaction.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/duplicate-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/duplicate-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
