# Archive All Modmail

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Utility](https://img.shields.io/badge/Category-Modmail-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Tool-8A2BE2?style=for-the-badge)

**Archive All Modmail** is a professional utility designed to safely and efficiently clear massive modmail backlogs. Managing a subreddit with an overgrown inbox can be tedious and prone to timeouts; this tool handles queues of any size reliably in the background, ensuring your moderation team can maintain a clean inbox with just a single click.

## Key Features

- **Background Processing**: Bypasses browser timeouts and UI freezing by delegating the heavy lifting to asynchronous background jobs. It effortlessly clears thousands of modmail conversations while you focus on other tasks.
- **Smart Queue Targeting**: Highly configurable to target specific modmail states. Whether you want to clear the "New" queue, "In Progress", or "Highlighted", you have granular control over what gets archived.
- **Concurrency Protection**: Includes a robust locking mechanism to ensure only one active archiving session runs at a time, preventing duplicate actions or API rate limit collisions.

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/archive-all-mm-flowchart.png)

1. A moderator clicks the **Archive All Modmail (Background)** action from the subreddit's Mod Tools.
2. The app verifies that no other archiving session is currently running.
3. A background task is spawned that pulls modmail conversations in batches matching your configured state criteria.
4. Each batch is safely archived. The process repeats automatically until the queue is completely empty.
5. A summary report is dispatched to ModMail confirming the operation has finished.

## Setup & Configuration

1. **Install**: Add **Archive All Modmail** to your subreddit via the App Directory.
2. **App Settings**: Navigate to your subreddit's Mod Tools > App Settings > Archive All Modmail.
3. **Configure Targets**: Select the specific modmail states (e.g., New, In Progress) that you want the tool to archive when activated.
4. **Usage**: Simply click the "Archive All Modmail (Background)" button in the sidebar Mod Tools to begin the clearing process.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/archive-all-mm/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/archive-all-mm/PRIVACY.md)

---
*Built for Reddit's moderator community.*
