# Sticky Pro

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Tool-8A2BE2?style=for-the-badge)

**Sticky Pro** is a high-performance moderation tool designed to streamline the repetitive process of posting and stickying recurring comments on new threads. Instead of keeping a notepad of common moderator responses, Sticky Pro allows your team to deploy pre-configured, formatted comments instantly with a single click natively from the Reddit interface.

## Key Features

- **Template System**: Configure up to three unique sticky templates with custom labels and full markdown content directly in the App Settings.
- **Direct Menu Items**: Dedicated post-menu actions for each template—no popup form required. Works natively on all Reddit platforms (Desktop, iOS, Android).
- **Auto-Sticky Posting**: Can be configured to automatically submit and lock a sticky comment on *every* new post in the subreddit, with built-in deduplication to prevent double-posting.
- **Reliable Deliveries**: Automatically retries and bypasses platform rate limits when posting, ensuring your moderation actions never fail silently.
- **Command Fail-safe**: Robust moderator commands (`!sticky 1`, `!sticky 2`) available as an additional, reliable trigger if the Mod Menu is ever inaccessible.

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/sticky-pro-flowchart.png)

1. A moderator selects one of their configured Sticky templates from a post's Mod Menu, OR a new post triggers the auto-sticky feature.
2. Sticky Pro retrieves the markdown template from your settings.
3. It posts the comment, distinguishing it as an official moderator action, sticking it to the top of the thread, and locking it to prevent user replies.
4. If Reddit's servers are busy, the app queues the action and retries automatically until successful.

## Setup & Configuration

1. **Install**: Add **Sticky Pro** to your subreddit via the App Directory.
2. **App Settings**: 
   - Navigate to your subreddit's Mod Tools > App Settings > Sticky Pro.
   - Define your Markdown text for Template 1, 2, and 3.
   - Set the custom labels for the Mod Menu (e.g., "Sticky Rule 1 Warning").
3. **Usage**: Access the tool by selecting your newly named sticky templates from the Mod Actions menu on any post in your community.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/sticky-pro/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/sticky-pro/PRIVACY.md)

---
*Built for Reddit's moderator community.*
