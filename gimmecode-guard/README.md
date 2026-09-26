> **User Guide & Overview** | [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/gimmecode-guard)

# GimmeCode Guard 🛡️

> **Filter low-effort code requests and protect constructive technical discussions across developer subreddits.**

GimmeCode Guard safeguards programming, Android/iOS, and creator subreddits from repetitive "give me code" demands, homework begging, and low-effort copy-paste requests. Powered by a real-time Webview Control Center, pattern scoring matrix, and Markdown code-block awareness, it nudges users toward constructive inquiry while preserving meaningful technical discussions.

### Key Highlights
- **Interactive Webview Control Center**: Real-time moderation dashboard embedded in a dedicated custom post for live audit feeds, metric counters, and instant configuration.
- **Three-Tier Escalation Lifecycle**: Progressive enforcement from polite educational warning replies to modqueue review reports and automated removals with archivable Modmail alerts.
- **Context-Aware Code Immunity**: Automatically exempts comments containing genuine Markdown code fences or indented blocks, creator fulfillment replies ("code sent", "dm sent"), and post authors (OP).
- **Interactive Comment Simulator**: Test phrase dictionaries, word-count heuristics, and score verdicts directly inside the Webview playground before saving changes.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/gimmecode-guard-flowchart.png)

### The 4-Step Lifecycle

1. **Submission & Ingestion**: A comment is submitted in the subreddit and delivered to the GimmeCode Guard server trigger.
2. **Context & Immunity Evaluation**: GimmeCode Guard verifies exemptions—skipping post authors in their own submissions (OP), community moderators, creator fulfillment replies ("code sent", "dm sent"), and comments containing valid Markdown code blocks.
3. **Multi-Token Phrase Scoring**: Brief low-effort comments (4 words or fewer) matching request patterns ("code please", "send source", "apk please") accumulate violation points in Redis with 90-day strike persistence.
4. **Graduated Escalation & Dashboard Sync**: The configured action (Tier 1 polite warning reply, Tier 2 modqueue report, or Tier 3 removal) executes immediately, and the violation record streams to the Webview audit feed.

---

## Quick Setup (60-Second Onboarding)

1. **Install**: Add **GimmeCode Guard** to your subreddit via the Reddit App Directory.
2. **Launch Dashboard**: Open the subreddit menu (`...`) and click **GimmeCode Guard Dashboard** to open the interactive control center.
3. **Configure Thresholds**: Review or adjust Tier 1 Warning, Tier 2 Report, and Tier 3 Removal point thresholds directly in the Webview.
4. **Test & Enforce**: Test custom community expressions in the Comment Playground. Automated protection activates immediately across all new comment submissions.

---

## Core Capabilities

- **Real-Time Webview Audit Feed**: Replaces awkward Modmail dumps with an interactive, searchable data table displaying flagged authors, comment snippets, score breakdowns, and action verdicts.
- **Graduated Moderation Actions**: Configure independent score thresholds for automated polite educational warnings (default: 3 pts), modqueue review reports (default: 9 pts), or direct public removals (default: 15 pts).
- **Interactive Comment Playground**: Live sandbox where moderators can test sample comments and verify word counts, matched phrases, and projected verdicts before saving rules.
- **Rolling 90-Day Strike Memory**: Tracks author violation strikes in Redis over 90-day rolling windows to identify habitual freeloaders while honoring author right-to-be-forgotten upon comment deletion.
- **Creator Fulfillment Immunity**: Automatically detects creator fulfillment replies ("code sent", "dm sent", "check inbox") so authors distributing requested materials are never penalized.

---

## The Old Way vs. The GimmeCode Guard Way

| Traditional Workflow | With GimmeCode Guard |
| :--- | :--- |
| Comment sections flooded with repetitive "send code" begging | **Automated phrase scoring** filtering low-effort requests instantly |
| Manual, repetitive warning comments explaining rule requirements | **Automated educational replies** politely guiding users to ask better questions |
| Accidental filter flags on legitimate code explanations | **Markdown code-block awareness** exempting genuine code snippets |
| Static Modmail dumps flooding moderator inboxes with raw text | **Interactive Webview Dashboard** with searchable audit logs and live stats |
| Guessing how a new rule or keyword phrase will perform | **Live Comment Playground** simulating score verdicts before activation |

---

## Designed to Assist Moderators

GimmeCode Guard detects and scores low-effort code requests to assist in maintaining technical discussion standards. Scoring serves as an assistive filter—human moderators maintain full authority to review flagged comments, approve exceptions, and adjust detection sensitivity at any time.

---

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

---

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/gimmecode-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/gimmecode-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
