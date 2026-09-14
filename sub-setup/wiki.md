# Sub Setup

Category: Moderation  
Version: v0.0.2  
Visibility: Unlisted  
Summary: Comprehensive subreddit setup guide and configuration auditor.

## Overview
Comprehensive subreddit setup guide and configuration auditor.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/sub-setup-flowchart.png)

## Key Features
- Interactive 9-Step Wizard: Structured progression from community identity and AutoModerator to rules, flairs, safety filters, onboarding, team health, and operations.
- Mod-Only Stealth Post: Runs in an expanded custom post that is automatically removed from the public subreddit feed so it never clutters member views.
- Persistent Manual Checklists: Tracks your manual verification progress in Redis (`v1` namespace), completely decoupled from API audit runs so you never lose progress.
- Optimistic UI Updates: Checkboxes update instantaneously with automatic rollback and toast notifications on network interruption.
- Batch Step Completion: "Mark All Complete in This Step" allows rapid completion of verified configuration areas.
- Remaining Items Quick Filter: 1-click modal listing all pending tasks across the entire subreddit with direct jump navigation.
- Rate-Limited Audit Engine: 60-second cooldown protects platform resources and displays live retry timers.
- Direct Mod Tools Launchers: Every section includes deep links with confirmed or best-effort routing to the exact Mod Tools page.
- Official Documentation: 30+ official Reddit Help Center and AutoModerator documentation links categorized by relevance.
- Zero-PII & Privacy-First: Reads only high-level community settings; never inspects private user profiles, post bodies, or modmail conversations.
- On-Demand Modmail Delivery: Safe multi-part chunking (under 9,000 characters per message) delivers formatted reports to team Mod Discussions on demand.

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
- Key patterns: node:http

## Setup and Usage
- ![Platform](https://img.shields.io/badge/Platform-Reddit%20Devvit-FF4500?style=flat-square)
- ![Category](https://img.shields.io/badge/Category-Moderation-blue?style=flat-square)
- ![Interface](https://img.shields.io/badge/Interface-Interactive%20Webview-00f2fe?style=flat-square)
- Interactive subreddit setup guide and configuration wizard for Reddit communities.
- `sub-setup` guides moderators through an in-depth, 19-section setup across 9 progressive wizard steps. It combines automated API inspections with persistent manual checklists, direct 1-click Mod Tools launchers, official Reddit documentation references, prioritized quick wins, and on-demand Modmail export.
- ![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/sub-setup-flowchart.png)
- Moderator Launch: A moderator clicks Run Subreddit Setup Audit in the subreddit menu. The server retrieves or generates a private, stealth custom post accessible only to moderators.
- Dual Audit & Interactive Wizard: The app loads an interactive 9-step React webview. Automated checks inspect 8 API-accessible areas, while guided checklists track manual settings with Redis persistence.
- Step-by-Step Configuration: Moderators work through settings, check off manual tasks with optimistic UI updates, launch 1-click Mod Tools deep links, or batch-complete steps.
- Export & Sharing: On demand, moderators can dispatch a structured Markdown summary directly to Modmail (Mod Discussions) or copy progress snippets to clipboard for team coordination.
- Interactive 9-Step Wizard: Structured progression from community identity and AutoModerator to rules, flairs, safety filters, onboarding, team health, and operations.
- Mod-Only Stealth Post: Runs in an expanded custom post that is automatically removed from the public subreddit feed so it never clutters member views.
- Persistent Manual Checklists: Tracks your manual verification progress in Redis (`v1` namespace), completely decoupled from API audit runs so you never lose progress.
- Optimistic UI Updates: Checkboxes update instantaneously with automatic rollback and toast notifications on network interruption.
- Batch Step Completion: "Mark All Complete in This Step" allows rapid completion of verified configuration areas.
- Remaining Items Quick Filter: 1-click modal listing all pending tasks across the entire subreddit with direct jump navigation.
- Rate-Limited Audit Engine: 60-second cooldown protects platform resources and displays live retry timers.
- Direct Mod Tools Launchers: Every section includes deep links with confirmed or best-effort routing to the exact Mod Tools page.
- Official Documentation: 30+ official Reddit Help Center and AutoModerator documentation links categorized by relevance.
- Zero-PII & Privacy-First: Reads only high-level community settings; never inspects private user profiles, post bodies, or modmail conversations.
- On-Demand Modmail Delivery: Safe multi-part chunking (under 9,000 characters per message) delivers formatted reports to team Mod Discussions on demand.
- Install Sub Setup on your subreddit.
- Open your subreddit's menu and select Run Subreddit Setup Audit.
- You will be routed directly to the interactive setup guide.
- Complete the 9 steps at your own pace — your progress is saved automatically.
- When ready, click Send to Modmail in Step 9 to archive your setup report in Mod Discussions.
- Step 1 — Community Identity & Settings: Title, description, sidebar length, community avatar, banner image, discoverability, and NSFW status.
- Step 2 — AutoModerator Protection: Wiki configuration existence, rule blocks, YAML syntax validation (tab detection), new account filtering, and action reasons.
- Step 3 — Rules Hub & Enforcement: Rule definitions, depth, rule fatigue checks, removal reasons, and pre-submission Post Check triggers.
- Step 4 — Flairs & Taxonomy: Post flair enablement, template counts, user flair enablement, media uploads, and wiki pages.
- Step 5 — Safety Filters & Auto-Triage: Native Crowd Control, Reputation Filter, Ban Evasion Filter, and Poster Eligibility.
- Step 6 — Onboarding & Community Guide: New member welcome messages, resource links, flair prompts, saved responses, and temporary event overrides.
- Step 7 — Moderator Team & Notifications: Team coverage, single-point-of-failure redundancy analysis, scoped permissions, and activity alert thresholds.
- Step 8 — Operations & Insights: Queue daily triage routines, Mod Log audit trails, Modmail workflow, and Mod Insights traffic growth.
- Step 9 — Final Review & Export: Overall score summary, remaining quick wins, progress reset, clipboard copy, and Modmail export.
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
0.0.2 — 2026-09-14
- Standard fleet synchronization and maintenance.

0.0.1 — 2026-09-14
- Standard fleet synchronization and maintenance.

1.0.1 — 2026-09-14
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/sub-setup/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/sub-setup/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/sub-setup)
- [Support](https://www.reddit.com/r/grantdb)