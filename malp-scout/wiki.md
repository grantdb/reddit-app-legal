MALP-Scout
Category: Moderation
Version: v0.0.17
Visibility: Unlisted
Summary: Manual-only Stargate SG-1 content scout for subreddit moderators.

Overview
Manual-only Stargate SG-1 content scout for subreddit moderators.

Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/malp-scout-flowchart.png)

Key Features
- Manual On-Demand Reconnaissance: Triggered strictly by subreddit moderators via the Mod Menu (`MALP: Launch Reconnaissance`). Zero automatic posting or background schedulers.
- Local Curated SG-1 Knowledge Base: Built-in, hand-reviewed dataset mapping SG-1 main/recurring cast birthdays, notable episode air dates, and major show milestones.
- Strict Zero-Crossover Policy: Enforces strict SG-1-only filtering, excluding Stargate Atlantis (SGA) and Stargate Universe (SGU) crossover content.
- Importance Quality Floor: Allows moderators to select a quality threshold (High, Medium, Low). Returns fewer candidates if not enough items meet the quality floor—never pads with weak filler.
- Moderator Preview & Approval Gate: Presents candidate titles, quality ranks, and 200-character excerpts in a confirmation form before any post is created on the subreddit.

Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)

Triggers and Activation
Event Triggers
- Not documented yet.

Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

Settings Reference
- editedTitle (string, default: defaultTitle): Post Title - Post Title
- editedBody (paragraph, default: defaultBody): Post Body (Markdown) - Post Body (Markdown)
- markAsSpoiler (boolean, default: false): Mark post as spoiler - Mark post as spoiler
- useDefaultMalpFlair (boolean, default: true): Apply default MALP post flair - Apply default MALP post flair
- selectedCandidateId (select, default: [options[0].value]): Select Candidate Post - Select Candidate Post

Automation Capabilities
- Submits Automated Comments: No
- Attaches Removal Notes: No
- Approves Content: No
- Removes or Filters Content: Yes
- Dispatches Modmail Alerts: No
- Updates User or Post Flair: No

Data Storage
This app does not store state in Redis.

Setup and Usage
- Install: Add MALP-Scout to your subreddit via the Devvit App Directory.
- Usage: Open the Subreddit Mod Menu (desktop) or tap the 3-dots on any post menu (mobile) and select MALP: Launch Reconnaissance.
- Select & Edit: Pick your preferred candidate post, customize the title or body markdown if desired.
- Publish: Tap Publish Post Now to submit to the subreddit.

Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.

Version History
0.0.17 — 2026-08-16
- Standard fleet synchronization and maintenance.
0.0.16 — 2026-08-16
- Optimize modal form transition with direct candidate JSON payload handoff.
- Implement atomic submitPost with integrated flairId to prevent client request timeouts.
0.0.15 — 2026-08-16
- Fix candidate selection algorithm to implement dynamic daily rotation across episodes/actors and balanced multi-category slotting (Actor Spotlight, Episode Focus, and Milestone Anniversary).

Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/malp-scout/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/malp-scout/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/malp-scout)