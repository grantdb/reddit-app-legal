# Sub Setup

Category: Moderation  
Version: v0.0.13  
Visibility: Unlisted  
Summary: Comprehensive subreddit setup guide and configuration auditor.

## Overview
Comprehensive subreddit setup guide and configuration auditor.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/sub-setup-flowchart.png)

## Key Features
- Not documented yet.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- Run Subreddit Setup Audit: Moderator menu action (Location: subreddit)

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- includeSuggestions: Include fix suggestions (boolean, default: true). Show actionable recommendations for each issue found in the report
- showDocLinks: Show documentation links (boolean, default: true). Include official Reddit documentation links in the report
- showDeepLinks: Show Mod Tools links (boolean, default: true). Include direct links to each Mod Tools section for quick access

## Automation Capabilities
- Submits Automated Comments: No — Does not submit automated comments.
- Attaches Removal Notes: No — Does not attach removal notes.
- Approves Content: No — Does not approve content.
- Removes or Filters Content: Yes — Removes or filters non-compliant submissions.
- Dispatches Modmail Alerts: Yes — Sends modmail notifications.
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Key patterns: node:http, sub-setup:toast

## Setup and Usage
- ![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
- ![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
- ![Security](https://img.shields.io/badge/Security-Hardened-red?style=for-the-badge)
- ![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
- ![Type](https://img.shields.io/badge/Type-Setup_Wizard-8A2BE2?style=for-the-badge)
- Step-by-step interactive setup wizard, live configuration audits, and Mod Tools guidance for Reddit communities.**
- Sub Setup guides new and experienced moderators through a comprehensive 19-section setup across 9 progressive wizard steps. It combines automated API inspections with persistent manual checklists, direct 1-click Mod Tools launchers, official Reddit documentation references, prioritized quick wins, and on-demand Modmail export.
- In-webview Setup Wizard: Interactive React webview embedded directly within Reddit, opened via your subreddit menu.
- Mod-only stealth post: Automatically removed from the public feed so it remains 100% private to your moderator team.
- Persistent Redis checklists: Check off manual tasks with instant optimistic UI updates, safely decoupled from API audit re-runs.
- Click Mod Tools launchers: Direct deep links to modern Mod Tools (`/mod/...`), including General Settings, Content Controls, Rules Hub, Safety Filters, and Modmail.
- Batch step completion: Mark all manual checklist items in a step complete with one click.
- Remaining items filter: Dedicated modal listing all incomplete items across all 9 steps with instant jump navigation.
- Rate-limited audit engine: 60-second cooldown protects platform resources and displays live retry countdowns.
- On-demand Modmail dispatch: Export structured, zero-emoji Markdown reports directly to Subreddit Mod Discussions.
- Dual-Score Integrity: Separates automated API inspections (which contribute to your numeric configuration score) from guided manual checklists and optional programs.
- Official Documentation: 30+ official Reddit Help Center and AutoModerator documentation links categorized by relevance.
- Zero-PII & Privacy-First: Inspects only public community configuration flags and rules; never inspects private user profiles, post bodies, or modmail conversations.
- Clean Plain-Text Formatting: Formatted with high-contrast, professional labels without emojis for clear readability across all Reddit clients.
- Continue Where You Left Off: Restores your active step and checklist state upon returning to the guide.
- Demo Mode: Allows previewing sample community data and guided steps even without moderator privileges.
- ![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/sub-setup-flowchart.png)
- Moderator Launch: A moderator clicks Run Subreddit Setup Audit in the subreddit menu. The server retrieves or generates a private, stealth custom post accessible only to moderators.
- Dual Audit & Interactive Wizard: The app loads an interactive 9-step React webview. Automated checks inspect 8 API-accessible areas, while guided checklists track manual settings with Redis persistence.
- Step-by-Step Configuration: Moderators work through settings, check off manual tasks with optimistic UI updates, launch 1-click Mod Tools deep links, or batch-complete steps.
- Export & Sharing: On demand, moderators can dispatch a structured Markdown summary directly to Modmail (Mod Discussions) or copy progress snippets to clipboard for team coordination.
- Step 1 — Community Identity & Settings: Title, description, sidebar length, community avatar, banner image, discoverability, and NSFW status.
- Step 2 — AutoModerator Protection: Wiki configuration existence, rule blocks, YAML syntax validation (tab detection), new account filtering, and action reasons.
- Step 3 — Rules Hub & Enforcement: Rule definitions, depth, rule fatigue checks, removal reasons, and pre-submission Post Check triggers.
- Step 4 — Flairs & Taxonomy: Post flair enablement, template counts, user flair enablement, media uploads, and wiki pages.
- Step 5 — Safety Filters & Auto-Triage: Native Crowd Control, Reputation Filter, Ban Evasion Filter, and Poster Eligibility.
- Step 6 — Onboarding & Community Guide: New member welcome messages, resource links, flair prompts, saved responses, and temporary event overrides.
- Step 7 — Moderator Team & Notifications: Team coverage, single-point-of-failure redundancy analysis, scoped permissions, and activity alert thresholds.
- Step 8 — Operations & Insights: Queue daily triage routines, Mod Log audit trails, Modmail workflow, and Mod Insights traffic growth.
- Step 9 — Final Review & Export: Overall score summary, remaining quick wins, progress reset, clipboard copy, and Modmail export.
- Install Sub Setup on your subreddit.
- Open your subreddit's menu and select Run Subreddit Setup Audit.
- You will be routed directly to the interactive setup guide.
- Complete the 9 steps at your own pace — your progress is saved automatically.
- When ready, click Send to Modmail in Step 9 to archive your setup report in Mod Discussions.
- For help, bug reports, or feature requests, post in r/grantdb.
- Please include the app name, what you expected, what happened, and any error text or screenshots.
- This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/sub-setup/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/sub-setup/PRIVACY.md)
- Built for Reddit's moderator community.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.13 — 2026-09-16
- Standard fleet synchronization and maintenance.

0.0.10 — 2026-09-15
- Standard fleet synchronization and maintenance.

0.0.9 — 2026-09-15
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/sub-setup/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/sub-setup/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/sub-setup)
- [Support](https://www.reddit.com/r/grantdb)