# AutoMod Easy

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Dev_Suite-8A2BE2?style=for-the-badge)

**AutoMod Easy** is an interactive development suite designed to help subreddit moderators learn, write, test, and optimize AutoModerator rules in a safe sandbox environment. Rather than testing complex YAML on a live subreddit and risking mistakes, moderators can build and verify their rules through an intuitive, visual interface.

## Key Features

- **Sandbox Lab**: A safe, isolated environment where you can write and test your rules against dummy posts without affecting your live subreddit.
- **Rule Advisor**: Automatically scans your live AutoModerator configuration for syntax errors, logical conflicts, or optimization opportunities.
- **Snapshots & Restore**: Automatically backs up your active configuration, allowing you to instantly roll back to a previous snapshot if a new rule causes unexpected issues.
- **Reverse Generator**: Simply paste the text of a problematic post or comment, and the suite will reverse-engineer and generate the AutoMod code needed to catch it.
- **Rule Presets**: Access a library of standard, proven presets for toxicity control, spam protection, and account age/karma filtering.

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/automod-easy-flowchart.png)

1. Access the AutoMod Easy dashboard from your Mod Tools.
2. Navigate to the Sandbox Lab to write a new rule or use the Reverse Generator.
3. The engine simulates how Reddit's AutoModerator would interpret your YAML against a specific scenario.
4. If satisfied, you can safely deploy the rule. If a mistake is made live, use the Snapshot tab to revert instantly.

## Setup & Configuration

1. **Install**: Add **AutoMod Easy** to your subreddit via the App Directory.
2. **Dashboard Initialization**: Navigate to your subreddit's Mod Tools and click on the AutoMod Easy app.
3. **Usage**: The app functions entirely within its Custom Post Dashboard. Use the tabs at the top of the interface to switch between the Sandbox, Advisor, and Backup tools.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/automod-easy/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/automod-easy/PRIVACY.md)

---
*Built for Reddit's moderator community.*
