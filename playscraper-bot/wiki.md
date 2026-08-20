Playscraper Bot
Category: Metadata
Version: v1.0.136
Visibility: Public
Summary: AI-powered metadata extraction via Gemini 2.5. Eligibility-first processing with configurable delay. Security-hardened moderator gates.

Overview
AI-powered metadata extraction via Gemini 2.5. Eligibility-first processing with configurable delay. Security-hardened moderator gates.

Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/playscraper-bot-flowchart.png)

Key Features
- Multi-Source Detection: Seamlessly identifies links from the Google Play Store, F-Droid, GitHub, GitLab, and Codeberg.
- AI-Powered Summaries: Integrates with Gemini 2.5 Flash to rapidly extract key metrics like developer name, download counts, categories, user ratings, and content ratings.
- Eligibility-First Processing: Employs a sophisticated delayed-processing pattern. It waits a configurable amount of time to confirm a new post is still live (not caught by Reddit's spam filters or AutoModerator) before making any expensive external API calls, saving your quota.
- Automated or Manual Automation: Can run automatically on all new posts, or be set to manual mode where it only scans when a moderator clicks "Trigger App Scraper" in the Mod menu.
- Configurable Detail Levels: Tailor the output comment's length by choosing between "Confirmed Only", "General Details", or "Full Details".

Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)
- http: External HTTP Fetch access [Domains: generativelanguage.googleapis.com, play.google.com, f-droid.org, github.com, gitlab.com, codeberg.org]

Triggers and Activation
Event Triggers
- PostSubmit: Delivered by Reddit event router to endpoint /internal/on-post-submit.
- PostCreate: Delivered by Reddit event router to endpoint /internal/on-post-create.
- ModAction: Delivered by Reddit event router to endpoint /internal/on-mod-action.
- AppInstall: Subscribed in main.ts via Devvit.addTrigger({ event: 'AppInstall' }).
- AppUpgrade: Subscribed in main.ts via Devvit.addTrigger({ event: 'AppUpgrade' }).

Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

Settings Reference
- process_post_delayed (group, default: -): Legal Documentation - Legal Documentation
- gemini_api_key (string, default: -): Automation Mode - Get a free API key from Google AI Studio (aistudio.google.com).
- comment_detail_level (select, default: -): Confirmed Only (badge + link) - Confirmed Only (badge + link)
- enabled_sources (select, default: -): Google Play Store - Google Play Store
- delayedProcessingEnabled (boolean, default: true): Processing Delay (seconds) - When enabled, the bot waits before processing a new post. It checks if the post is still valid before calling external APIs.
- skipIfRemoved (boolean, default: true): Skip if Post is Filtered (In Modqueue) - If the post is removed by the time the bot checks, skip processing entirely.
- skipIfSpam (boolean, default: true): Trigger App Scraper - If the post is marked as spam when the bot checks, skip processing.

Automation Capabilities
- Submits Automated Comments: Yes
- Attaches Removal Notes: No
- Approves Content: No
- Removes or Filters Content: No
- Dispatches Modmail Alerts: No
- Updates User or Post Flair: No

Data Storage
This app utilizes Reddit Redis storage:
- Key-Value Strings (deduplication & cooldown markers)
- Key Patterns: og:title

Setup and Usage
- Install: Add Playscraper Bot via the App Directory.
- API Key Requirement: Obtain a free Google Gemini API Key from Google AI Studio.
- App Settings:
- Input your Gemini API Key into the app settings.
- Choose which sources to detect (e.g., enable GitHub but disable Play Store).
- Set your preferred Comment Detail Level.
- Monitoring: The bot operates silently in the background unless configured for Manual mode.

Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.

Version History
1.0.136 — 2026-08-15
- Standard fleet synchronization and maintenance.
1.0.135 — 2026-08-15
- Standard fleet synchronization and maintenance.
1.0.134 — 2026-08-11
- Standard fleet synchronization and maintenance.

Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/playscraper-bot/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/playscraper-bot/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/playscraper-bot)