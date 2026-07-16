# AI Checker

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Security-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-AI_Analyzer-8A2BE2?style=for-the-badge)

**AI Checker** is a manual moderation utility designed to help community moderators identify and manage AI-generated content. Rather than scanning every post automatically, it empowers moderators to selectively scan suspicious posts directly from the native Reddit interface and leave automated, customizable comments with the results.

## Key Features

- **Multi-Provider Support**: Choose your preferred detection engine. Currently integrated with:
  - **GPTZero**
  - **Hive Moderation**
  - **Sightengine**
- **Standardized Scoring**: Normalizes complex confidence percentages from various APIs into a simple, easy-to-understand 1-10 scale.
- **Customizable Templates**: Full control over the result comments using dynamic text templates.
- **Modmail Alerts**: Optional setting to send a notification to modmail for every detection result, keeping the whole team in the loop.

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/ai-checker-flowchart.png)

1. A moderator spots a suspicious post and selects the **Scan for AI** action from the post's mod menu.
2. The app extracts the text and sends it to your configured detection provider.
3. The app normalizes the response and replies to the post with a stickied comment detailing the likelihood that the text is AI-generated.

## Setup & Configuration

1. **Install**: Add **AI Checker** to your subreddit via the App Directory.
2. **Provider Key**: Obtain an API key from your chosen provider (GPTZero, Hive, or Sightengine).
3. **App Settings**: Navigate to your subreddit's Mod Tools > App Settings > AI Checker.
4. **Configure**:
   - Select your Detection Provider from the dropdown.
   - Enter your API Key.
   - (Optional) Customize the result comment template and toggle modmail alerts.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/ai-checker/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/ai-checker/PRIVACY.md)

## Fetch Domains

The following domains are requested for this app to communicate with external detection engines:
- `api.gptzero.me` - Used to fetch AI detection scores from the GPTZero engine.
- `api.thehive.ai` - Used to fetch AI detection scores from Hive Moderation.
- `api.sightengine.com` - Used to fetch AI detection scores from the Sightengine API endpoint.
- `generativelanguage.googleapis.com` - Global allowlist domain used for Gemini API integrations.

---
*Built for Reddit's moderator community.*
