DistroFeed Bot
Category: Automation
Version: v0.1.105
Visibility: Public
Summary: Linux aggregator. Upgraded to Gemini 2.5 metadata extraction. Fixed network permissions.

Overview
Linux aggregator. Upgraded to Gemini 2.5 metadata extraction. Fixed network permissions.

Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/DistroFeed-bot-flowchart.png)

Key Features
- % Manual & Moderator Control: Zero auto-posting or background crons. Operates via a 2-stage Mod Menu workflow.
- AI-Powered Search Grounding: Uses Google Gemini 2.5 Flash to scan DistroWatch, Phoronix, and 9to5Linux for recent major OS releases and kernel updates.
- Interactive Pre-Publish Editor: Presents candidate updates in an interactive Devvit form where moderators can customize post title, target URL, TL;DR summary, post flair, and sticky comment options.
- Deduplication Engine: Enforces Redis URL and topic slug tracking to prevent duplicate coverage.

Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)
- http: External HTTP Fetch access [Domains: generativelanguage.googleapis.com]

Triggers and Activation
Event Triggers
- Not documented yet.

Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

Settings Reference
- gemini_api_key (string, default: tr): Include Major Releases - Required. Get yours at aistudio.google.com. Used for all source scanning.
- include_serious_updates (boolean, default: true): Post Title - Post significant updates: kernel releases, security patches.
- targetUrl (string, default: defaultUrl): Post Link URL - Post Link URL
- editedSummary (paragraph, default: defaultBody): TL;DR Summary (Comment Text) - TL;DR Summary (Comment Text)
- flairText (string, default: defaultFlair): Post Flair Text - Post Flair Text
- postStickyComment (boolean, default: true): Submit TL;DR summary as sticky comment - Submit TL;DR summary as sticky comment
- selectedIndex (select, default: options.length): Select Linux Update Candidate - Select Linux Update Candidate

Automation Capabilities
- Submits Automated Comments: Yes
- Attaches Removal Notes: No
- Approves Content: No
- Removes or Filters Content: Yes
- Dispatches Modmail Alerts: No
- Updates User or Post Flair: Yes

Data Storage
This app utilizes Reddit Redis storage:
- Key-Value Strings (deduplication & cooldown markers)
- Sorted Sets (time-series audit logs)
- Key Patterns: distrofeed:scouted_candidates, distrofeed:posted_urls

Setup and Usage
- Install: Add DistroFeed Bot to your subreddit via the App Directory.
- App Settings: Navigate to Mod Tools > App Settings > DistroFeed Bot and provide a Google Gemini API Key (from aistudio.google.com).
- Usage: Open the subreddit Mod Menu to scout and review updates.

Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.

Version History
0.1.105 — 2026-08-15
- Standard fleet synchronization and maintenance.
0.1.104 — 2026-08-09
- Standard fleet synchronization and maintenance.
0.1.103 — 2026-08-08
- Standard fleet synchronization and maintenance.

Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/distrofeed-bot/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/distrofeed-bot/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/distrofeed-bot)