Post Title Check
Category: Validation
Version: v0.0.81
Visibility: Public
Summary: Real-time title validation against community guidelines. Now with support for customizable removal reasons per rule.

Overview
Real-time title validation against community guidelines. Now with support for customizable removal reasons per rule.

Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/post-title-check-flowchart.png)

Key Features
- Not documented yet.

Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

Triggers and Activation
Event Triggers
- PostSubmit: Delivered by Reddit event router to endpoint /internal/on-post-submit.
- PostCreate: Delivered by Reddit event router to endpoint /internal/on-post-create.
- AppInstall: Subscribed in main.ts via Devvit.addTrigger({ event: 'AppInstall' }).
- AppUpgrade: Subscribed in main.ts via Devvit.addTrigger({ event: 'AppUpgrade' }).

Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

Settings Reference
- legal_docs (string, default: See): Terms & Privacy - Terms & Privacy

Automation Capabilities
- Submits Automated Comments: Yes
- Attaches Removal Notes: No
- Approves Content: No
- Removes or Filters Content: Yes
- Dispatches Modmail Alerts: No
- Updates User or Post Flair: No

Data Storage
This app utilizes Reddit Redis storage:
- Key-Value Strings (deduplication & cooldown markers)

Setup and Usage
- Install: Add Post Title Check to your subreddit through the Reddit App Directory.
- Configure Rules: Open Mod Tools > App Settings > Post Title Check to set word counts and required tags.
- Add Banned Words: Enter prohibited clickbait phrases separated by commas.
- Save: Automated title validation begins immediately on all incoming community submissions.
- No complex AutoMod regex scripts required. Clean, professional titles across your entire feed.*

Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.

Version History
0.0.81 — 2026-08-15
- Standard fleet synchronization and maintenance.
0.0.80 — 2026-08-15
- Standard fleet synchronization and maintenance.
0.0.79 — 2026-08-11
- Standard fleet synchronization and maintenance.

Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/post-title-check/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/post-title-check/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/post-title-check)