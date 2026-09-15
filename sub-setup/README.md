> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/sub-setup)

# Sub Setup 🛠️

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Hardened-red?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Setup_Wizard-8A2BE2?style=for-the-badge)

> **Step-by-step interactive setup wizard, live configuration audits, and Mod Tools guidance for Reddit communities.**

Sub Setup guides new and experienced moderators through a comprehensive 19-section setup across 9 progressive wizard steps. It combines automated API inspections with persistent manual checklists, direct 1-click Mod Tools launchers, official Reddit documentation references, prioritized quick wins, and on-demand Modmail export.

---

## At a Glance

- **In-webview Setup Wizard**: Interactive React webview embedded directly within Reddit, opened via your subreddit menu.
- **Mod-only stealth post**: Automatically removed from the public feed so it remains 100% private to your moderator team.
- **Persistent Redis checklists**: Check off manual tasks with instant optimistic UI updates, safely decoupled from API audit re-runs.
- **1-Click Mod Tools launchers**: Direct deep links to `/about/edit`, `/wiki/config/automoderator`, `/about/rules`, and `/safety`.
- **Batch step completion**: Mark all manual checklist items in a step complete with one click.
- **Remaining items filter**: Dedicated modal listing all incomplete items across all 9 steps with instant jump navigation.
- **Rate-limited audit engine**: 60-second cooldown protects platform resources and displays live retry countdowns.
- **On-demand Modmail dispatch**: Export structured, zero-emoji Markdown reports directly to Subreddit Mod Discussions.

---

## The Old Way vs. The Sub Setup Way

| Traditional Workflow | With Sub Setup |
| :--- | :--- |
| Hunting through dozens of desktop Mod Tools menus | **9 guided wizard steps** with direct 1-click deep links to each setting |
| Guessing which settings AutoMod or Safety Filters need | **Automated API inspection** scoring live rules, flairs, and configuration |
| Losing track of which mod finished which setting | **Persistent Redis checklists** tracking team setup progress across sessions |
| Confusing manual settings with automated checks | **Clear visual badges and tooltips** distinguishing API vs. manual reviews |
| Forgetting pre-submission post checks or removal reasons | **Structured checklists** ensuring 1:1 rule-to-removal-reason parity |
| Static, overwhelming wall-of-text audit dumps | **Interactive wizard with progress gauges**, remaining items modal, and Modmail export |

---

## Built for Seamless Subreddit Onboarding

- **Dual-Score Integrity**: Separates automated API inspections (which contribute to your numeric configuration score) from guided manual checklists and optional programs.
- **Official Documentation**: 30+ official Reddit Help Center and AutoModerator documentation links categorized by relevance.
- **Zero-PII & Privacy-First**: Inspects only public community configuration flags and rules; never inspects private user profiles, post bodies, or modmail conversations.
- **Clean Plain-Text Formatting**: Formatted with high-contrast, professional labels without emojis for clear readability across all Reddit clients.
- **Continue Where You Left Off**: Restores your active step and checklist state upon returning to the guide.
- **Demo Mode**: Allows previewing sample community data and guided steps even without moderator privileges.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/sub-setup-flowchart.png)

### Your Four-Step Workflow

1. **Moderator Launch**: A moderator clicks **Run Subreddit Setup Audit** in the subreddit menu. The server retrieves or generates a private, stealth custom post accessible only to moderators.
2. **Dual Audit & Interactive Wizard**: The app loads an interactive 9-step React webview. Automated checks inspect 8 API-accessible areas, while guided checklists track manual settings with Redis persistence.
3. **Step-by-Step Configuration**: Moderators work through settings, check off manual tasks with optimistic UI updates, launch 1-click Mod Tools deep links, or batch-complete steps.
4. **Export & Sharing**: On demand, moderators can dispatch a structured Markdown summary directly to Modmail (Mod Discussions) or copy progress snippets to clipboard for team coordination.

---

## 9 Wizard Steps (19 Configuration Sections)

1. **Step 1 — Community Identity & Settings**: Title, description, sidebar length, community avatar, banner image, discoverability, and NSFW status.
2. **Step 2 — AutoModerator Protection**: Wiki configuration existence, rule blocks, YAML syntax validation (tab detection), new account filtering, and action reasons.
3. **Step 3 — Rules Hub & Enforcement**: Rule definitions, depth, rule fatigue checks, removal reasons, and pre-submission Post Check triggers.
4. **Step 4 — Flairs & Taxonomy**: Post flair enablement, template counts, user flair enablement, media uploads, and wiki pages.
5. **Step 5 — Safety Filters & Auto-Triage**: Native Crowd Control, Reputation Filter, Ban Evasion Filter, and Poster Eligibility.
6. **Step 6 — Onboarding & Community Guide**: New member welcome messages, resource links, flair prompts, saved responses, and temporary event overrides.
7. **Step 7 — Moderator Team & Notifications**: Team coverage, single-point-of-failure redundancy analysis, scoped permissions, and activity alert thresholds.
8. **Step 8 — Operations & Insights**: Queue daily triage routines, Mod Log audit trails, Modmail workflow, and Mod Insights traffic growth.
9. **Step 9 — Final Review & Export**: Overall score summary, remaining quick wins, progress reset, clipboard copy, and Modmail export.

---

## Install / Use

1. Install **Sub Setup** on your subreddit.
2. Open your subreddit's menu and select **Run Subreddit Setup Audit**.
3. You will be routed directly to the interactive setup guide.
4. Complete the 9 steps at your own pace — your progress is saved automatically.
5. When ready, click **Send to Modmail** in Step 9 to archive your setup report in Mod Discussions.

---

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

---

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/sub-setup/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/sub-setup/PRIVACY.md)

---
*Built for Reddit's moderator community.*
