# MALP-Scout

Category: Moderation  
Version: v0.0.19  
Visibility: Unlisted  
Summary: Manual-only Stargate SG-1 content scout for subreddit moderators.

## Overview
Manual-only Stargate SG-1 content scout for subreddit moderators.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/malp-scout-flowchart.png)

## Key Features
- Manual On-Demand Reconnaissance: Triggered strictly by subreddit moderators via the Mod Menu (`MALP: Launch Reconnaissance`). Zero automatic posting or background schedulers.
- Local Curated SG-1 Knowledge Base: Built-in, hand-reviewed dataset mapping SG-1 main/recurring cast birthdays, notable episode air dates, and major show milestones.
- Strict Zero-Crossover Policy: Enforces strict SG-1-only filtering, excluding Stargate Atlantis (SGA) and Stargate Universe (SGU) crossover content.
- Importance Quality Floor: Allows moderators to select a quality threshold (High, Medium, Low). Returns fewer candidates if not enough items meet the quality floor—never pads with weak filler.
- Moderator Preview & Approval Gate: Presents candidate titles, quality ranks, and 200-character excerpts in a confirmation form before any post is created on the subreddit.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)

## Triggers and Activation
### Menu Actions
- MALP: Launch Reconnaissance: Moderator menu action (Location: subreddit)
- MALP: Launch Reconnaissance: Moderator menu action (Location: post)

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- editedTitle: Post Title (string, default: defaultTitle). Post Title
- editedBody: Post Body (Markdown) (paragraph, default: defaultBody). Post Body (Markdown)
- markAsSpoiler: Mark post as spoiler (boolean, default: false). Mark post as spoiler
- useDefaultMalpFlair: Apply default MALP post flair (boolean, default: true). Apply default MALP post flair
- selectedCandidateId: Select Candidate Post (select, default: [options[0].value]). Select Candidate Post

## Automation Capabilities
- Submits Automated Comments: No — Does not submit automated comments.
- Attaches Removal Notes: No — Does not attach removal notes.
- Approves Content: No — Does not approve content.
- Removes or Filters Content: Yes — Removes or filters non-compliant submissions.
- Dispatches Modmail Alerts: No — Does not send modmail notifications.
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app does not store persistent state in Redis.

## Setup and Usage
- Install: Add MALP-Scout to your subreddit via the Devvit App Directory.
- Usage: Open the Subreddit Mod Menu (desktop) or tap the 3-dots on any post menu (mobile) and select MALP: Launch Reconnaissance.
- Select & Edit: Pick your preferred candidate post, customize the title or body markdown if desired.
- Publish: Tap Publish Post Now to submit to the subreddit.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.19 — 2026-09-02
- Standard fleet synchronization and maintenance.

0.0.18 — 2026-08-27
- Fix milestone rotation modulo lock and expand curated knowledge dataset

0.0.17 — 2026-08-16
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/malp-scout/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/malp-scout/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/malp-scout)
- [Support](https://www.reddit.com/r/grantdb)