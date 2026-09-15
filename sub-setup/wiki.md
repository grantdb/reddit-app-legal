# Sub Setup

Category: Moderation  
Version: v0.0.7  
Visibility: Unlisted  
Summary: Comprehensive subreddit setup guide and configuration auditor.

## Overview
Comprehensive subreddit setup guide and configuration auditor.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/sub-setup-flowchart.png)

## Key Features
- Not documented yet.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- Run Subreddit Setup Audit: Moderator menu action (Location: subreddit)

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- includeSuggestions: Include fix suggestions (boolean, default: true). Show actionable recommendations for each issue found in the report
- showDocLinks: Show documentation links (boolean, default: true). Include official Reddit documentation links in the report
- showDeepLinks: Show Mod Tools links (boolean, default: true). Include direct links to each Mod Tools section for quick access

## Automation Capabilities
- Submits Automated Comments: No — Does not submit automated comments.
- Attaches Removal Notes: No — Does not attach removal notes.
- Approves Content: No — Does not approve content.
- Removes or Filters Content: Yes — Removes or filters non-compliant submissions.
- Dispatches Modmail Alerts: Yes — Sends modmail notifications.
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Key patterns: node:http

## Setup and Usage
- | Traditional Workflow | With Sub Setup |
- | :--- | :--- |
- | Hunting through dozens of desktop Mod Tools menus | 9 guided wizard steps with direct 1-click deep links to each setting |
- | Guessing which settings AutoMod or Safety Filters need | Automated API inspection scoring live rules, flairs, and configuration |
- | Losing track of which mod finished which setting | Persistent Redis checklists tracking team setup progress across sessions |
- | Confusing manual settings with automated checks | Clear visual badges and tooltips distinguishing API vs. manual reviews |
- | Forgetting pre-submission post checks or removal reasons | Structured checklists ensuring 1:1 rule-to-removal-reason parity |
- | Static, overwhelming wall-of-text audit dumps | Interactive wizard with progress gauges, remaining items modal, and Modmail export |

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.7 — 2026-09-15
- Standard fleet synchronization and maintenance.

0.0.6 — 2026-09-15
- Standard fleet synchronization and maintenance.

0.0.5 — 2026-09-15
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/sub-setup/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/sub-setup/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/sub-setup)
- [Support](https://www.reddit.com/r/grantdb)