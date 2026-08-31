# Playscraper Bot

Category: Metadata  
Version: v1.0.137  
Visibility: Public  
Summary: AI-powered metadata extraction via Gemini 2.5. Eligibility-first processing with configurable delay. Security-hardened moderator gates.

## Overview
AI-powered metadata extraction via Gemini 2.5. Eligibility-first processing with configurable delay. Security-hardened moderator gates.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/playscraper-bot-flowchart.png)

## Key Features
- Multi-Source Detection: Seamlessly identifies links from the Google Play Store, F-Droid, GitHub, GitLab, and Codeberg.
- Cost & Pricing Transparency: Highlights app pricing (Free, Paid) and in-app purchase requirements directly in summary comments.
- AI-Powered Summaries: Integrates with Gemini 2.5 Flash to rapidly extract key metrics like developer name, download counts, categories, user ratings, and content ratings.
- Eligibility-First Processing: Employs a sophisticated delayed-processing pattern. It waits a configurable amount of time to confirm a new post is still live (not caught by Reddit's spam filters or AutoModerator) before making any expensive external API calls, saving your quota.
- Automated or Manual Automation: Can run automatically on all new posts, or be set to manual mode where it only scans when a moderator clicks "Trigger App Scraper" in the Mod menu.
- Configurable Detail Levels: Tailor the output comment's length by choosing between "Confirmed Only", "General Details", or "Full Details".

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)
- http: External HTTP Fetch access [Domains: generativelanguage.googleapis.com, play.google.com, f-droid.org, github.com, gitlab.com, codeberg.org]

## Triggers and Activation
### Menu Actions
- Playscraper Bot: Scan Post: Manually run the scraper bot on this post (Location: post)

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- legal_docs: Terms & Privacy (string, default: See help text for official documentation links.). https://github.com/grantdb/reddit-app-legal/tree/main/playscraper-bot
- gemini_api_key: Google Gemini API Key (string, default: -). Get a free API key from Google AI Studio (aistudio.google.com).
- automation_mode: Automation Mode (select, default: auto). Select whether the bot should automatically process new posts or only run when manually triggered.
- comment_detail_level: Comment Detail Level (select, default: general). Controls how much information the bot includes in its comment. "General" shows key stats; "Full" adds IAPs, updated date, and an AI-generated description.
- enabled_sources: App Sources to Detect (select, default: playstore,github,fdroid). Select which app stores and repositories the bot will detect and look up. Disabled sources are silently ignored.
- delayedProcessingEnabled: Enable Delayed Processing (boolean, default: true). When enabled, the bot waits before processing a new post. It checks if the post is still valid before calling external APIs.
- delayedProcessingSeconds: Processing Delay (seconds) (number, default: 20). How many seconds to wait before checking a new post (min: 5, max: 100). Default: 20.
- skipIfRemoved: Skip if Post is Removed (boolean, default: true). If the post is removed by the time the bot checks, skip processing entirely.
- skipIfFiltered: Skip if Post is Filtered (In Modqueue) (boolean, default: true). If the post is filtered (awaiting mod approval) when the bot checks, skip processing.
- skipIfSpam: Skip if Post is Marked as Spam (boolean, default: true). If the post is marked as spam when the bot checks, skip processing.

## Automation Capabilities
- Submits Automated Comments: Yes — Posts automated comments on target submissions.
- Attaches Removal Notes: No — Does not attach removal notes.
- Approves Content: No — Does not approve content.
- Removes or Filters Content: No — Does not remove or filter content.
- Dispatches Modmail Alerts: No — Does not send modmail notifications.
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Key patterns: og:title

## Setup and Usage
- Install: Add Playscraper Bot via the App Directory.
- API Key Requirement: Obtain a free Google Gemini API Key from Google AI Studio.
- App Settings:
- Input your Gemini API Key into the app settings.
- Choose which sources to detect (e.g., enable GitHub but disable Play Store).
- Set your preferred Comment Detail Level.
- Monitoring: The bot operates silently in the background unless configured for Manual mode.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
1.0.137 — 2026-08-31
- Standard fleet synchronization and maintenance.

1.0.136 — 2026-08-15
- Standard fleet synchronization and maintenance.

1.0.135 — 2026-08-15
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/playscraper-bot/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/playscraper-bot/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/playscraper-bot)
- [Support](https://www.reddit.com/r/grantdb)