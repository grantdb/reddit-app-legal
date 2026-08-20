CanuckNews Bot
Category: News
Version: v1.1.39
Visibility: Public
Summary: Regional Canadian news aggregation with moderator triggers.

Overview
Regional Canadian news aggregation with moderator triggers.

Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/CanuckNews-bot-flowchart.png)

Key Features
- % Manual & Moderator Control: Operates strictly on-demand. The bot will never auto-post or run background crons.
- Candidate Scouting Pipeline: Interactively scans CBC, Global News, and Globe & Mail feeds based on your selected subject focus (Health, Science, Tech, Business, Lifestyle, Regional).
- Pre-Publish Editor: Presents candidate stories in an interactive Devvit form allowing moderators to inspect and customize the post title, link URL, flair, and spoiler settings before publishing.
- Content & Spam Filtering: Automatically filters out political content and controversial topics to maintain a neutral community environment.
- Day Redis Deduplication: Prevents duplicate link submissions across all scouting runs.

Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)
- http: External HTTP Fetch access [Domains: www.cbc.ca, cbc.ca, globalnews.ca, www.theglobeandmail.com, theglobeandmail.com]

Triggers and Activation
Event Triggers
- Not documented yet.

Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

Settings Reference
- legal_docs (string, default: See): Terms & Privacy - Terms & Privacy
- flair_national (string, default: -): Canada / National Flair ID - Canada / National Flair ID
- flair_bc (string, default: -): British Columbia Flair ID - British Columbia Flair ID
- flair_ab (string, default: -): Alberta Flair ID - Alberta Flair ID
- flair_prairies (string, default: -): Sask/Manitoba Flair ID - Sask/Manitoba Flair ID
- flair_on (string, default: -): Ontario Flair ID - Ontario Flair ID
- flair_qc (string, default: -): Quebec Flair ID - Quebec Flair ID
- flair_atlantic (string, default: -): Atlantic Flair ID - Atlantic Flair ID
- flair_north (string, default: -): North/Territories Flair ID - North/Territories Flair ID
- editedTitle (string, default: defaultTitle): Post Title - Post Title
- targetUrl (string, default: defaultUrl): Article URL - Article URL
- flairId (string, default: ): Flair ID (Optional) - Flair ID (Optional)
- markAsSpoiler (boolean, default: false): Mark post as spoiler - Mark post as spoiler
- selectedCandidateId (select, default: options.length): Select Article to Review & Edit - Select Article to Review & Edit
- postCount (select, default: [3]): Candidate Pool Size - Candidate Pool Size
- subject_filters (select, default: -): Subject Focus - Subject Focus

Automation Capabilities
- Submits Automated Comments: No
- Attaches Removal Notes: No
- Approves Content: No
- Removes or Filters Content: Yes
- Dispatches Modmail Alerts: No
- Updates User or Post Flair: No

Data Storage
This app utilizes Reddit Redis storage:
- Key-Value Strings (deduplication & cooldown markers)
- Key Patterns: canucknews:scouted

Setup and Usage
- Install: Add Canuck News Bot to your subreddit via the App Directory.
- App Settings: Navigate to Mod Tools > App Settings > Canuck News Bot to map optional regional post flair IDs.
- Usage: Open the subreddit Mod Menu and click Scout Canadian News to begin scouting.

Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.

Version History
1.1.39 — 2026-08-15
- Standard fleet synchronization and maintenance.
1.1.38 — 2026-08-09
- Standard fleet synchronization and maintenance.
1.1.37 — 2026-08-08
- Standard fleet synchronization and maintenance.

Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/canucknews-bot/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/canucknews-bot/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/canucknews-bot)