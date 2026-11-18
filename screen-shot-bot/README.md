> **User Guide & Overview** | [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/screen-shot-bot)

# Screen Shot Bot

> **Automated AI OCR and terminal-log transcription engine for technical support communities.**

**Screen Shot Bot** bridges the gap between technical image uploads and searchable community data. Rather than forcing users to manually re-type long error logs from a photo, it uses Google Gemini Vision (`gemini-3.5-flash-lite`) to transcribe text from terminal windows, boot logs, and configuration screens into clean, indexable comments.

---

## At a Glance

- **Automated AI Transcription**: Uses Gemini Vision to extract text from complex, grainy, or poorly lit technical screenshots.
- **Searchable Indexing**: Converts static crash-log images into formatted code-block comments so future users can search for the same errors.
- **Configurable Targets**: Restrict transcription to specific categories (Errors & Crash Logs, System Info, Config Files) or allow all terminal images.
- **Mod Approval Coverage**: Safely re-processes held posts if they are later approved by a moderator, plus on-demand Mod Menu extraction.

---

## How It Works: The 4-Step Operational Pipeline

### 01 · Image Post Detection

> **Submission & Mod-Approval Triggers**
> - Monitors new image posts and moderator-approved posts in the subreddit.
> - Downloads and base64-encodes the image for AI inspection.

---

### 02 · Target Classification

> **Contextual Filtering**
> - Evaluates the image against your configured Extraction Target (e.g., Errors & Crash Logs).
> - Skips non-matching images cleanly without posting noise.

---

### 03 · OCR Extraction

> **Gemini Vision Transcription**
> - Extracts terminal output, stack traces, or configuration lines into structured JSON rows.
> - Uses `gemini-3.5-flash-lite` with `gemini-3.6-flash` fallback and rate-limit protection.

---

### 04 · Formatted Reply

> **Indexable Code-Block Comment**
> - Posts the transcribed text in a clean Markdown code block on the submission.
> - Supports on-demand re-runs via the post's **Extract text from image (Gemini)** mod menu action.

---

## Quick Setup

1. **Install**: Add **Screen Shot Bot** to your subreddit via the Reddit App Directory.
2. **Configure API Key & Target**: Open **Mod Tools > App Settings > Screen Shot Bot**, add your Google Gemini API key, and select an Extraction Target.
3. **Verify**: Submit a test terminal screenshot or trigger **Extract text from image (Gemini)** from a post's mod menu.

---

## Support

> **Official Support Community**
> - Post questions, bug reports, or feature requests in [https://www.reddit.com/r/grantdb](https://www.reddit.com/r/grantdb).
> - Include the app name, what you expected, what happened, and any error text or screenshots.
> - [Full User Guide](https://www.reddit.com/r/grantdb/wiki/screen-shot-bot/)
> - [Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/screen-shot-bot/)

---

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/screen-shot-bot/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/screen-shot-bot/PRIVACY.md)

---
*Built for Reddit's moderator community.*
