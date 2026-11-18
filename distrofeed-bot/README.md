> **User Guide & Overview** | [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/distrofeed-bot)

# DistroFeed Bot

> **Manual-only Linux release curation and candidate scouting engine for Reddit moderators.**

**DistroFeed Bot** is a manual-only candidate-scouting and pre-editing curator built for Linux and open-source subreddits. It leverages Google Gemini AI with search grounding to scout major Linux distribution releases and technical updates, allowing moderators to inspect, edit, and post clean, summarized community updates.

---

## At a Glance

- **100% Manual & Moderator Control**: Zero auto-posting or background crons. Operates strictly via an interactive Mod Menu popout workflow.
- **AI-Powered Search Grounding**: Uses Google Gemini (`gemini-3.5-flash-lite`) with search grounding to scan DistroWatch, Phoronix, and 9to5Linux for recent major OS releases and kernel updates.
- **Interactive Pre-Publish Editor**: Presents candidate updates in an interactive Devvit form where moderators can customize post title, target URL, TL;DR summary, post flair, and sticky comment options.
- **Deduplication Engine**: Enforces Redis URL and topic slug tracking to prevent duplicate coverage across runs.

---

## How It Works: The 4-Step Operational Pipeline

### 01 · Scout Updates

> **Manual Trigger & Background AI Scan**
> - Open the subreddit menu (`...`), select **DistroFeed Bot**, and choose **1. Scout Updates** to start background AI scanning.
> - Queries DistroWatch, Phoronix, and 9to5Linux via Gemini search grounding and stores fresh candidates in Redis.

---

### 02 · Review Candidates

> **Interactive Candidate Picker**
> - After ~90 seconds, open **DistroFeed Bot** and choose **2. Review & Publish**.
> - Deduplicated candidates are presented in a clean selection form for moderator review.

---

### 03 · Customize Details

> **Pre-Publish Editor**
> - Review and customize the post title, target link URL, TL;DR summary, post flair, and optional sticky comment.
> - Confirm all details before anything is published to the subreddit.

---

### 04 · Publish & Track

> **Atomic Post & Dedupe Recording**
> - Click **Publish Post Now** to submit the curated post and optional sticky comment.
> - Records the URL and topic slug in Redis so the same release is not surfaced again.

---

## Quick Setup

1. **Install**: Add **DistroFeed Bot** to your subreddit via the Reddit App Directory.
2. **Configure API Key**: Navigate to **Mod Tools > App Settings > DistroFeed Bot** and provide a Google Gemini API Key (from `aistudio.google.com`).
3. **Run on Demand**: Open the subreddit menu (`...`), click **DistroFeed Bot**, and scout or review updates on your schedule.

---

## Support

> **Official Support Community**
> - Post questions, bug reports, or feature requests in [https://www.reddit.com/r/grantdb](https://www.reddit.com/r/grantdb).
> - Include the app name, what you expected, what happened, and any error text or screenshots.
> - [Full User Guide](https://www.reddit.com/r/grantdb/wiki/distrofeed-bot/)
> - [Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/distrofeed-bot/)

---

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/DistroFeed-bot/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/DistroFeed-bot/PRIVACY.md)

---
*Built for Reddit's moderator community.*
