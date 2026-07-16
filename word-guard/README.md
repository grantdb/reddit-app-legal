# GuardHub: Word Guard 🛡️

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Content_Policy-8A2BE2?style=for-the-badge)

**Word Guard** is a comprehensive keyword moderation engine that replaces complex AutoModerator YAML scripts with a structured, easy-to-use visual management dashboard. It allows moderation teams to quickly deploy, organize, and test profanity filters, slur blocklists, and anti-spam keyword rules without needing to write a single line of code.

## Key Features

- **Structured Rule Groups**: Logically organize your blocked keywords into distinct groups (e.g., "Profanity", "T-Shirt Scams", "Politics") so your team can manage them independently without digging through a massive block of text.
- **Regex Support**: Full support for advanced Regular Expressions for when simple keyword matching isn't enough, allowing you to catch complex obfuscated text.
- **Audit Logging**: Safely test new keyword rules in "Audit Mode" before enforcing them live. Review a history of all matched rules in the dashboard to ensure you aren't catching innocent conversation.
- **Private Dashboard**: A fully secure, moderator-only Custom Post Dashboard built natively into Reddit for managing rules on the fly via mobile or desktop.

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/word-guard-flowchart.png)

1. A user submits text (a post body, title, or comment) to the subreddit.
2. Word Guard extracts the text and runs it through your enabled Rule Groups.
3. If a keyword or regex pattern matches the text, the app executes the action configured for that group (Remove, Filter to Modqueue, or simply Audit Log).
4. The action is recorded in the dashboard for the moderation team to review.

## Setup & Configuration

1. **Install**: Add **Word Guard** to your subreddit via the App Directory.
2. **Dashboard Initialization**: Navigate to your subreddit's Mod Tools and open the GuardHub: Word Guard Dashboard.
3. **Configure Rules**: 
   - Open the Rules tab to create your first keyword group.
   - Enter your target words and choose an action (we recommend starting with "Filter" or "Audit").
4. **Monitoring**: Check the Dashboard logs periodically to ensure your keyword rules are catching the right content.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/word-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/word-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
