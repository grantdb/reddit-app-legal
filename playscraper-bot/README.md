> **User Guide & Overview** | [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/playscraper-bot)

# Playscraper Bot

> **Instantly extract, summarize, and display app store metadata, cost, and developer details for community submissions.**

**Playscraper Bot** is a moderator utility that leverages AI to extract and summarize metadata from app stores and open-source repositories. By automatically posting standardized, informative comment headers on submissions containing links to these platforms, it helps moderators and users verify shared software content at a glance.

---

## At a Glance

- **Multi-Source Detection**: Identifies links from the Google Play Store, F-Droid, GitHub, GitLab, and Codeberg.
- **Cost & Pricing Transparency**: Highlights app pricing (Free, Paid) and in-app purchase requirements directly in summary comments.
- **AI-Powered Summaries**: Integrates with Gemini to extract key metrics like developer name, download counts, categories, user ratings, and content ratings.
- **Eligibility-First Processing**: Waits a configurable delay to confirm a new post is still live (or auto-processes immediately when a moderator approves a queued post) before making external API calls.
- **Manual Scan & Link Override**: Moderators can trigger **Playscraper Bot: Scan Post** or **Playscraper Bot: Enter App Link** directly from the post menu.
- **Configurable Detail Levels**: Choose between "Confirmed Only", "General Details", or "Full Details".

---

## How It Works: The 5-Step Operational Pipeline

### 01 · Detect Submission
> **Post, comment, or moderator approval trigger**
> - A user posts a link to a supported app store or repository, or a moderator approves a queued post or triggers **Scan Post** / **Enter App Link**.

---

### 02 · Eligibility Gate
> **Delayed spam and removal check**
> - The bot waits the configured delay (bypassed on moderator approval) and confirms the post was not removed by Reddit's filters or AutoModerator.

---

### 03 · Fetch Source HTML
> **Bounded external metadata retrieval**
> - If eligible, Playscraper Bot fetches the target store or repository page with a bounded timeout and parses structured HTML tags.

---

### 04 · AI Extraction
> **Isolated Gemini metadata synthesis**
> - Parsed tags and sanitized HTML are sent to Gemini with untrusted-data isolation to extract standardized metadata.

---

### 05 · Post Summary
> **Distinguished sticky comment**
> - A formatted, stickied moderator comment summarizing the app is posted to the thread.

---

## Quick Setup

1. **Install**: Add **Playscraper Bot** via the Reddit App Directory.
2. **Configure API Key**: Obtain a Google Gemini API Key from Google AI Studio and add it in **Mod Tools > App Settings > Playscraper Bot**.
3. **Customize**: Choose enabled sources, delay settings, and your preferred Comment Detail Level.

---

## Support

> **Need Help?** Post in [https://www.reddit.com/r/grantdb](https://www.reddit.com/r/grantdb) with the app name, what you expected, what happened, and any error text or screenshots.
>
> - **User Guide**: [https://www.reddit.com/r/grantdb/wiki/playscraper-bot/](https://www.reddit.com/r/grantdb/wiki/playscraper-bot/)
> - **Technical Reference**: [https://www.reddit.com/r/grantdb/wiki/index/all-apps/playscraper-bot/](https://www.reddit.com/r/grantdb/wiki/index/all-apps/playscraper-bot/)

---

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/playscraper-bot/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/playscraper-bot/PRIVACY.md)

---
*Built for Reddit's moderator community.*
