AI Checker
Category: Security
Version: v0.0.81
Visibility: Public
Summary: Moderator-triggered AI detection engine. Upgraded to native Gemini 1.5 Flash for high-speed analysis.

Overview
Moderator-triggered AI detection engine. Upgraded to native Gemini 1.5 Flash for high-speed analysis.

Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/ai-checker-flowchart.png)

Key Features
- Not documented yet.

Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)
- http: External HTTP Fetch access [Domains: generativelanguage.googleapis.com, api.gptzero.me, api.sightengine.com, api.thehive.ai, i.redd.it, preview.redd.it, external-preview.redd.it, i.imgur.com]

Triggers and Activation
Event Triggers
- PostCreate: Subscribed in main.ts via Devvit.addTrigger({ event: 'PostCreate' }).

Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.tsx)

Settings Reference
- check_ai_post_eligibility (group, default: -): Provider Configuration - Provider Configuration

Automation Capabilities
- Submits Automated Comments: Yes
- Attaches Removal Notes: No
- Approves Content: No
- Removes or Filters Content: No
- Dispatches Modmail Alerts: Yes
- Updates User or Post Flair: No

Data Storage
This app utilizes Reddit Redis storage:
- Key-Value Strings (deduplication & cooldown markers)

Setup and Usage
- Install: Add AI Checker to your subreddit through the Reddit App Directory.
- Configure Provider: Open Mod Tools > App Settings > AI Checker and add your provider API key.
- Set Preferences: Choose between on-demand menu auditing or automated background scanning.
- Save: Start evaluating synthetic content directly from your native moderation workflow.
- No external browser extensions required. Multi-model AI detection right inside Reddit.*

Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.

Version History
0.0.81 — 2026-08-15
- Standard fleet synchronization and maintenance.
0.0.80 — 2026-08-02
- Standard fleet synchronization and maintenance.
0.0.79 — 2026-08-02
- Standard fleet synchronization and maintenance.

Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/ai-checker/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/ai-checker/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/ai-checker)