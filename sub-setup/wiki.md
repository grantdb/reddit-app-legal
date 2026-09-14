# Sub Setup

Category: Moderation  
Version: v0.0.1  
Visibility: Unlisted  
Summary: Comprehensive subreddit setup guide and configuration auditor.

## Overview
Comprehensive subreddit setup guide and configuration auditor.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/sub-setup-flowchart.png)

## Key Features
- Dual-Score Integrity: Separates API-inspected settings (which contribute to your numeric configuration score) from guided manual reviews and optional features.
- Direct Mod Tools Links: Every section includes direct links with confirmed or best-effort routing and fallback URLs to the exact settings page.
- Official Documentation: 30+ official Reddit Help Center and AutoModerator documentation links categorized by relevance.
- Zero-PII & Privacy-First: Reads only high-level community settings; never inspects private user profiles, post bodies, or modmail conversations.
- Clean Plain-Text Formatting: Formatted with high-contrast, professional labels without emojis for clear readability across all Reddit clients.
- Automatic Modmail Delivery: Seamless chunking ensures reports exceeding Reddit character limits arrive as cleanly sequenced parts.

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

## Setup and Usage
- ![Reddit](https://img.shields.io/badge/Platform-Reddit%20Devvit-FF4500?style=flat-square)
- ![Category](https://img.shields.io/badge/Category-Moderation-blue?style=flat-square)
- Comprehensive subreddit setup guide and configuration auditor for Reddit communities.
- `sub-setup` performs an in-depth, 19-section audit of your subreddit configuration, providing direct Mod Tools deep links, official Reddit documentation references, prioritized quick wins, and structured checklists. The completed audit report is formatted cleanly and delivered privately to your subreddit's Modmail (Mod Discussions).
- ![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/sub-setup-flowchart.png)
- Moderator Action: A moderator selects Run Subreddit Setup Audit from the subreddit menu.
- Dual Audit Engine: The engine runs batched API execution for 8 verified sections with error isolation, followed by 11 guided manual reviews and optional checks.
- Dual-Score Processing: The app calculates an API-inspected score (0-100%), extracts top priorities and quick wins, and caches audit state in Redis.
- Modmail Delivery: Safe multi-part chunking (under 9,000 characters per message) delivers formatted reports directly to team Mod Discussions.
- Dual-Score Integrity: Separates API-inspected settings (which contribute to your numeric configuration score) from guided manual reviews and optional features.
- Direct Mod Tools Links: Every section includes direct links with confirmed or best-effort routing and fallback URLs to the exact settings page.
- Official Documentation: 30+ official Reddit Help Center and AutoModerator documentation links categorized by relevance.
- Zero-PII & Privacy-First: Reads only high-level community settings; never inspects private user profiles, post bodies, or modmail conversations.
- Clean Plain-Text Formatting: Formatted with high-contrast, professional labels without emojis for clear readability across all Reddit clients.
- Automatic Modmail Delivery: Seamless chunking ensures reports exceeding Reddit character limits arrive as cleanly sequenced parts.
- Install Sub Setup on your subreddit.
- Open your subreddit's menu and select Run Subreddit Setup Audit.
- A toast will confirm that the audit is running.
- Check your subreddit's Modmail (Mod Discussions)** for the complete audit report.
- Basic Settings and Community Identity: Title, description, sidebar length, community avatar, banner image, discoverability, and NSFW status.
- AutoModerator: Wiki configuration existence, rule blocks, YAML syntax validation (tab detection), new account filtering, and action reasons.
- Post and User Flairs: Post flair enablement, template counts, user flair enablement, and assignment permissions.
- Community Rules: Rule definitions, depth, rule fatigue checks, descriptions, and custom report reasons.
- Removal Reasons: Reason definitions, 1:1 rule mapping, explanatory depth, and appeal instructions.
- Wiki and Documentation: Wiki enablement, index landing page presence, and documentation pages.
- Moderator Team and Permissions: Team size, single-point-of-failure redundancy analysis, and scoped permissions.
- Posting and Content Settings: Allowed submission types, media uploads, crossposting, spoilers, and restriction status.
- Rules Hub and Post Check: Pre-submission rule warnings and keyword trigger checks.
- Poster Eligibility and Requirements: Native account age, karma, and verified email requirements.
- Safety Filters: Crowd Control, Reputation Filter, Ban Evasion Filter, and Harassment filtering.
- Saved Responses: Standardized modmail replies, ban appeal templates, and macro consistency.
- Community Guide and Onboarding: New member welcome messages, resource links, and flair prompts.
- Temporary Events and Scheduled Posts: Setting overrides during traffic spikes and recurring posts.
- Moderator Notifications: Milestone alerts, activity spikes, and report threshold alerts.
- Queue, Reports, Mod Log, and Modmail Workflow: Operational triage routines and audit trails.
- Insights and Operational Health: Traffic growth, team health, and safety tool catch rates.
- Optional Reddit Programs and Training: Mod Guide training modules, app directory extensions, and contributor programs.
- Feature Availability and API Limitations: Overview of Devvit 0.14.2 API visibility and progressive rollout status.
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
0.0.1 — 2026-09-14
- Standard fleet synchronization and maintenance.

1.0.1 — 2026-09-14
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/sub-setup/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/sub-setup/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/sub-setup)
- [Support](https://www.reddit.com/r/grantdb)