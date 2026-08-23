# Guard Hub

Category: Moderation  
Version: v0.0.12  
Visibility: Unlisted  
Summary: Central GuardHub integration platform.

## Overview
Central GuardHub integration platform.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/guard-hub-flowchart.png)

## Key Features
- Not documented yet.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)

## Triggers and Activation
### Menu Actions
- GuardHub: Status: Moderator menu action (Location: subreddit)

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- placeholder: Placeholder Setting (string, default: Reserved for GuardHub). Placeholder Setting

## Automation Capabilities
- Submits Automated Comments: No — Does not submit automated comments.
- Attaches Removal Notes: No — Does not attach removal notes.
- Approves Content: No — Does not approve content.
- Removes or Filters Content: No — Does not remove or filter content.
- Dispatches Modmail Alerts: No — Does not send modmail notifications.
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app does not store persistent state in Redis.

## Setup and Usage
- Install: Add Guard Hub to your subreddit through the Reddit App Directory.
- Open Hub: Launch GuardHub: Guard Hub Dashboard from Subreddit Mod Tools.
- Review: Guard Hub automatically discovers your installed apps and displays your community defense status.
- Monitor: Check the dashboard periodically to ensure all moderation layers remain fully operational.
- No complex configuration required. Complete observability for your entire moderation ecosystem.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.12 — 2026-08-15
- Standard fleet synchronization and maintenance.

0.0.11 — 2026-07-27
- Standard fleet synchronization and maintenance.

0.0.61 — 2026-07-27
- Configuration: Added `Devvit.configure({ redditAPI: true, redis: true })`.
- UX: Restricted Status menu item to moderators (`forUserType: 'moderator'`).

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/guard-hub/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/guard-hub/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/guard-hub)
- [Support](https://www.reddit.com/r/grantdb)