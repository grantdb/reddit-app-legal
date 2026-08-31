> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/sticky-pro)

# Sticky Pro

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Tool-8A2BE2?style=for-the-badge)

> **Deploy pre-configured templates, write ad-hoc markdown notes, schedule expiration timers, and manage sticky comments.**

**Sticky Pro** is a high-performance moderation tool designed to streamline the process of posting, customizing, and managing recurring sticky comments on community threads. Instead of keeping a notepad of common moderator responses, Sticky Pro allows your team to deploy pre-configured templates, write ad-hoc markdown notes, schedule auto-unsticky expiration timers, or remove active stickies natively from the Reddit interface.

---

## Key Features

- **Unified Post Menu Popout**: Open **Sticky Pro** from any post menu (`...`) to pick from configured templates, write custom markdown, toggle pinning and comment locks, set auto-unsticky timers, or remove active stickies.
- **One-Click Unsticky Action**: Select **Remove Active Sticky** inside the popout to immediately unpin and remove the active sticky comment and cancel any pending timers.
- **Duration Expiration Timers**: Automatically expire and remove sticky comments after a configurable countdown (1 hour, 6 hours, 12 hours, 24 hours, 3 days, 7 days) via scheduled background jobs.
- **Auto-Sticky Posting**: Can be configured to automatically submit and lock a sticky comment on every new post in the subreddit, with built-in deduplication and delayed eligibility checking.
- **Auto-Pin Control**: Configurable setting (`autoPin`) to control whether sticky comments are pinned to the top of the comment section or distinguished as moderator comments without pinning.
- **Enhanced Comment Commands**: Quick moderator commands (`!sticky 1 24h`, `!sticky 2 3d`, `!sticky 3`, `!unsticky`) available as fast mobile and desktop shortcuts.
- **Reliable Deliveries**: Automatically retries and bypasses platform rate limits when posting, ensuring your moderation actions never fail silently.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/sticky-pro-flowchart.png)

### Workflow Steps

1. **Trigger**: A moderator selects **Sticky Pro** from a post menu, triggers a comment command (`!sticky 1 24h`), OR a new post triggers the auto-sticky feature.
2. **Eligibility & Replacement**: For auto-sticky, Sticky Pro evaluates the Delayed Eligibility-First Gate. For manual posts, it automatically cleans up any previous sticky comment and timer on that post.
3. **Publish**: Sticky Pro retrieves the template markdown or custom input, distinguishes the comment as an official moderator action, pins it to top if requested, and locks it against user replies.
4. **Timer / Expiry**: If a duration timer is specified, a scheduled background job (`unsticky_timer`) automatically unpins/removes the sticky when time expires.
5. **Removal**: Selecting **Remove Active Sticky** in the popout or commenting `!unsticky` immediately cleans up the active sticky comment.

---

## Setup & Configuration

1. **Install**: Add **Sticky Pro** to your subreddit via the Reddit App Directory.
2. **App Settings**: 
   - Navigate to your subreddit's **Mod Tools > App Settings > Sticky Pro**.
   - Define your Markdown text and custom display labels for Template 1, 2, and 3.
   - Toggle **Enable Auto-Sticky on Every Post** and set **Pin Auto-Sticky Comment to Top** (`autoPin`).
   - Configure Delayed Eligibility-First processing preferences (delay duration, skip if removed, skip if spam).
3. **Usage**:
   - On any post, open the moderator menu (`...`), select **Sticky Pro**, and choose **Post / Customize Sticky** or **Remove Active Sticky**.
   - Use `!sticky 1 24h` or `!sticky 2` in comment replies for rapid mobile shortcuts.

---

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

---

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/sticky-pro/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/sticky-pro/PRIVACY.md)

---
*Built for Reddit's moderator community.*
