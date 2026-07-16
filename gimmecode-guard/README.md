# GuardHub: GimmeCode Guard 🛡️

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Automation-8A2BE2?style=for-the-badge)

**GimmeCode Guard** is an automated moderation tool for developer communities. It identifies low-effort comments that only ask for code (e.g. "code please", "send source") and takes action based on configurable thresholds to encourage higher-quality technical discussions.

## Key Features

- **Smart Detection**: Detects common phrases and fuzzy variations of "give me code" requests.
- **Context Aware**: Intelligently ignores valid questions and comments containing code blocks.
- **Configurable Thresholds**: Moderators can set custom scores to trigger a warning reply, report to mod queue, or remove the comment.
- **Repeat Offender Tracking**: Keeps track of user infractions across the subreddit.

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/gimmecode-guard-flowchart.png)

1. A user submits a comment to the subreddit.
2. GimmeCode Guard runs the text through its scoring engine.
3. If the comment matches low-effort code request patterns, it accumulates a score.
4. Based on the score and your configured thresholds, the app automatically executes the appropriate moderation action (Warn, Report, or Remove).

## Setup & Configuration

1. **Install**: Add **GimmeCode Guard** to your subreddit via the App Directory.
2. **Configuration**: Navigate to your subreddit's Mod Tools -> Installed Apps -> GimmeCode Guard.
3. **Configure Rules**: Set the `warnThreshold`, `reportThreshold`, and `removeThreshold` values (defaults are 0/disabled).
4. **Monitoring**: Review reported comments in the mod queue to ensure the app is functioning as expected.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/gimmecode-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/gimmecode-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
