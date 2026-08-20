Canadian News
Category: News
Version: v0.0.54
Visibility: Public
Summary: Regional Canadian news aggregator. Refactored to include political news as an optional subject.

Overview
Regional Canadian news aggregator. Refactored to include political news as an optional subject.

Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/canadian-news-flowchart.png)

Key Features
- % Manual Moderator Control: Zero auto-posting or background crons. You decide when news is scouted and published.
- Multi-Subject Scouting: Scout stories across Politics, Health, Science, Technology, Crime, Business, Lifestyle, or Regional news feeds.
- Pre-Publish Editor: Review scouted candidate stories in an interactive Devvit form to customize the post title, target URL, and spoiler tags prior to posting.
- Spam Filtering & Deduplication: Automatically filters promotional and spam content while enforcing 30-day link deduplication in Redis.

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
- editedTitle (string, default: defaultTitle): Post Title - Post Title
- targetUrl (string, default: defaultUrl): Article URL - Article URL
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
- Key Patterns: canadian-news:scouted

Setup and Usage
- Install: Add Canadian News App to your subreddit via the App Directory.
- Usage: Open the subreddit Mod Menu and click Scout Canadian News to launch the interactive scouting workflow.

Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.

Version History
0.0.54 — 2026-08-15
- Standard fleet synchronization and maintenance.
0.0.53 — 2026-08-09
- Standard fleet synchronization and maintenance.
0.0.52 — 2026-08-08
- Standard fleet synchronization and maintenance.

Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/canadian-news/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/canadian-news/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/canadian-news)