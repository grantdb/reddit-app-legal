> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/sub-setup)

# Sub Setup

## Purpose
Comprehensive subreddit setup guide and configuration auditor for Reddit communities.

`sub-setup` performs an in-depth, 19-section audit of your subreddit configuration, providing direct Mod Tools deep links, official Reddit documentation references, prioritized quick wins, and structured checklists. The completed audit report is formatted cleanly and delivered privately to your subreddit's Modmail (Mod Discussions).

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/sub-setup-flowchart.png)

### Your Four-Step Workflow

1. **Moderator Action**: A moderator selects **Run Subreddit Setup Audit** from the subreddit menu.
2. **Dual Audit Engine**: The engine runs batched API execution for 8 verified sections with error isolation, followed by 11 guided manual reviews and optional checks.
3. **Dual-Score Processing**: The app calculates an API-inspected score (0-100%), extracts top priorities and quick wins, and caches audit state in Redis.
4. **Modmail Delivery**: Safe multi-part chunking (under 9,000 characters per message) delivers formatted reports directly to team Mod Discussions.

## Major Features

- **Dual-Score Integrity**: Separates API-inspected settings (which contribute to your numeric configuration score) from guided manual reviews and optional features.
- **Direct Mod Tools Links**: Every section includes direct links with confirmed or best-effort routing and fallback URLs to the exact settings page.
- **Official Documentation**: 30+ official Reddit Help Center and AutoModerator documentation links categorized by relevance.
- **Zero-PII & Privacy-First**: Reads only high-level community settings; never inspects private user profiles, post bodies, or modmail conversations.
- **Clean Plain-Text Formatting**: Formatted with high-contrast, professional labels without emojis for clear readability across all Reddit clients.
- **Automatic Modmail Delivery**: Seamless chunking ensures reports exceeding Reddit character limits arrive as cleanly sequenced parts.

## Install / Use

1. Install **Sub Setup** on your subreddit.
2. Open your subreddit's menu and select **Run Subreddit Setup Audit**.
3. A toast will confirm that the audit is running.
4. Check your subreddit's **Modmail (Mod Discussions)** for the complete audit report.

## Audit Sections (19 Total)

### Part 1: API-Inspected Configuration (8 Sections)
1. **Basic Settings and Community Identity**: Title, description, sidebar length, community avatar, banner image, discoverability, and NSFW status.
2. **AutoModerator**: Wiki configuration existence, rule blocks, YAML syntax validation (tab detection), new account filtering, and action reasons.
3. **Post and User Flairs**: Post flair enablement, template counts, user flair enablement, and assignment permissions.
4. **Community Rules**: Rule definitions, depth, rule fatigue checks, descriptions, and custom report reasons.
5. **Removal Reasons**: Reason definitions, 1:1 rule mapping, explanatory depth, and appeal instructions.
6. **Wiki and Documentation**: Wiki enablement, index landing page presence, and documentation pages.
7. **Moderator Team and Permissions**: Team size, single-point-of-failure redundancy analysis, and scoped permissions.
8. **Posting and Content Settings**: Allowed submission types, media uploads, crossposting, spoilers, and restriction status.

### Part 2: Guided Manual Reviews (9 Sections)
9. **Rules Hub and Post Check**: Pre-submission rule warnings and keyword trigger checks.
10. **Poster Eligibility and Requirements**: Native account age, karma, and verified email requirements.
11. **Safety Filters**: Crowd Control, Reputation Filter, Ban Evasion Filter, and Harassment filtering.
12. **Saved Responses**: Standardized modmail replies, ban appeal templates, and macro consistency.
13. **Community Guide and Onboarding**: New member welcome messages, resource links, and flair prompts.
14. **Temporary Events and Scheduled Posts**: Setting overrides during traffic spikes and recurring posts.
15. **Moderator Notifications**: Milestone alerts, activity spikes, and report threshold alerts.
16. **Queue, Reports, Mod Log, and Modmail Workflow**: Operational triage routines and audit trails.
17. **Insights and Operational Health**: Traffic growth, team health, and safety tool catch rates.

### Part 3: Optional and Eligibility-Gated Features (2 Sections)
18. **Optional Reddit Programs and Training**: Mod Guide training modules, app directory extensions, and contributor programs.
19. **Feature Availability and API Limitations**: Overview of Devvit 0.14.2 API visibility and progressive rollout status.

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/sub-setup/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/sub-setup/PRIVACY.md)

---
*Built for Reddit's moderator community.*
