# Post Title Check

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Validation](https://img.shields.io/badge/Logic-Validation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Content_Policy-8A2BE2?style=for-the-badge)

**Post Title Check** is a powerful automation utility that rigorously enforces community editorial standards, ensuring your subreddit's feed remains highly organized, readable, and professional. It validates new submissions in real-time against your custom title rules and provides immediate, constructive feedback to users when they make a mistake, entirely removing the need for manual moderator intervention.

## Key Features

- **Configurable Rules Engine**: Easily set minimum word counts, ban specific phrases or clickbait terms, require categorization brackets (e.g., `[News]`), and restrict special characters.
- **Custom Removal Reasons**: Provide custom, multi-line explanations for each specific rule violation, ensuring users understand exactly what they did wrong. Supports a dynamic `{phrase}` injector to echo back the banned word they used.
- **Automated Removal & Messaging**: Violating posts are immediately removed from the feed. The author receives a detailed private message containing a "Copy & Resubmit" template so they can easily fix their title and try again.
- **Public Accountability**: Leaves a distinguished, sticky comment on the removed post explaining the rule violation for full transparency.

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/post-title-check-flowchart.png)

1. A user clicks submit on a new post.
2. The app intercepts the post before it gains traction and runs the title through your configured gauntlet of rules.
3. If a rule is broken, the post is instantly removed.
4. The user receives a private message with their original text and instructions on how to fix the title, reducing frustration and moderator modmail.

## Setup & Configuration

1. **Install**: Add **Post Title Check** to your subreddit via the App Directory.
2. **App Settings**: Navigate to your subreddit's Mod Tools > App Settings > Post Title Check.
3. **Configure Rules**: 
   - Define your formatting rules (e.g., Word Count > 4, Brackets Required).
   - Enter any banned phrases separated by commas.
4. **Customize Messaging**: Provide your own Custom Removal Reasons in the settings fields, or leave them blank to use the app's standard automated messaging.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/post-title-check/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/post-title-check/PRIVACY.md)

---
*Built for Reddit's moderator community.*
