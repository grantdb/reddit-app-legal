> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/archive-all-mm)

# Archive All Modmail

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Hardened-red?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Modmail-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Tool-8A2BE2?style=for-the-badge)

> **Clear massive modmail backlogs in the background with a single click.**

Archive All Modmail effortlessly clears overgrown subreddit inboxes without browser freezing or timeout errors. Running resilient chunked batch jobs in the background, it processes thousands of old modmail threads while your team stays focused on active community support.

---

## At a Glance

- **One-click background archiving**: Trigger bulk modmail cleanup from Subreddit Mod Tools.
- **Zero browser timeouts**: Delegated background execution runs smoothly without freezing your page.
- **Smart queue selection**: Choose whether to archive New, In Progress, Appeals, or custom queues.
- **Real-time run progress**: Check live archive statistics anytime from the moderator menu.
- **Rate-limited chunking**: Throttles API requests safely to prevent Reddit rate limit penalties.

---

## The Old Way vs. The Archive All Modmail Way

| Traditional Workflow | With Archive All Modmail |
| :--- | :--- |
| Clicking "Archive" manually hundreds of times per week | **One-click bulk archiving** processing thousands of threads in the background |
| Browser tab freezing and crashing on massive inboxes | **Asynchronous worker tasks** running independently of your browser session |
| Accidental archiving of internal mod discussions | **Smart API safety filters** automatically preserving mod-only discussions |
| Running into Reddit API rate limit locks during cleanup | **Batched, throttled chunking** keeping operations well within API boundaries |
| Wondering how many conversations were cleared | **Real-time status inspector** reporting exact processed thread counts |

---

## Built for Effortless Inbox Zero

- **Asynchronous Background Workers**: Offloads high-volume archiving operations to reliable server-side tasks so you can close your browser and move on.
- **Configurable Target Queues**: Select specific folders to clear (e.g. New, In Progress, Appeals) directly from App Settings.
- **Single-Session Concurrency Locks**: Uses Redis locking mechanisms to prevent duplicate concurrent runs or conflicting operations.
- **Live Progress Auditing**: Select **Check Modmail Archive Status** from the overflow menu to view running totals and completed batches.
- **Built-in Safety Protections**: Automatically identifies and protects restricted moderator discussions from bulk modifications.
- **Native Settings Control**: Fine-tune target queues and batch sizes directly from Subreddit Mod Tools.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/archive-all-mm-flowchart.png)

### Your Four-Step Workflow

1. **Trigger**: A moderator clicks **Archive All Modmail (Background)** from Subreddit Mod Tools.
2. **Lock**: Redis concurrency locks initialize a dedicated run session and verify target queues.
3. **Process**: Background workers pull conversations in 100-item batches and archive them in throttled 10-item chunks.
4. **Complete**: Workers loop automatically until selected queues reach Inbox Zero and report final counts.

---

## Quick Setup

1. **Install**: Add **Archive All Modmail** to your subreddit through the Reddit App Directory.
2. **Configure Queues**: Open **Mod Tools > App Settings > Archive All Modmail** and pick your target queues.
3. **Start Cleanup**: Click **Archive All Modmail (Background)** from the subreddit action menu.
4. **Monitor**: Check **Check Modmail Archive Status** anytime to observe real-time progress.

*No repetitive manual clicking. Safe, automated Inbox Zero in your native workflow.*

---

## Advanced Capabilities

Archive All Modmail is engineered for high-volume inbox processing and graceful rate-limit handling.

- **Throttled Batch Pipeline**: Fetches modmail threads in 100-conversation pages and executes archives in paced 10-item sub-chunks.
- **Recursive Task Rescheduling**: Automatically schedules continuation background jobs when conversation counts exceed single-execution quotas.
- **Redis Concurrency Mutex**: Prevents overlapping execution runs with atomic lock acquisition and automatic timeout expiry.
- **Restricted Thread Bypassing**: Detects API permission boundaries on internal moderator threads and skips them cleanly.

---

## Designed to Assist Moderators

Archive All Modmail automates bulk thread archiving across designated queues based on explicit moderator initiation. Archiving actions follow the exact target queues configured by your team—human moderators maintain full control over when cleanup tasks are started or paused.

---

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include:
- The app name.
- What you expected to happen.
- What happened instead.
- Any error message.
- Screenshots or relevant details.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/archive-all-mm/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/archive-all-mm/PRIVACY.md)

---
*Built for Reddit's moderator community.*
