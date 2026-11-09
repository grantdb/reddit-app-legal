# Mod Dispatch

Category: Moderation  
Version: v0.0.2  
Visibility: Unlisted  
Summary: Mod Dispatch adds shared ownership, live coordination, suggestions, and handoffs to the Reddit mod queue.

## Overview
Mod Dispatch adds shared ownership, live coordination, suggestions, and handoffs to the Reddit mod queue.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/moddispatch-flowchart.png)

## Key Features
- Claim for Review: Marks item as actively claimed. Automatically prevents simultaneous claims with informative collision notices ("This item is already claimed by u/example").
- Release Claim: Allows the claimant to return an item to the unclaimed queue with optional context (e.g., "Need more context", "Not my area").
- Inactivity Timeout: Claims automatically release back to the team after a configurable duration (10, 15, 30, or 60 minutes) if no action is taken.
- Senior Moderator Overrides: Senior moderators can safely override stale or stalled claims, with every override recorded in the immutable audit trail.
- Suggest to Another Mod: Routes cases to specific teammates with urgency flags (Normal, Needs review soon, Urgent) and contextual notes.
- Hand Off Ownership: Transfers active ownership during shift changes, preserving all prior notes, claim history, and audit events.
- Shared Moderator Notes: Attach private notes with quick presets ("Needs second opinion", "Waiting on user", "Repeat offender", "Escalate", "Needs rule clarification") or free text. Notes persist permanently.
- Team Escalation: Flag complex cases for senior review with standardized escalation categories (safety/legal, rule changes, repeated abuse, appeals).
- Standard Non-Scrollable Status Page: Strict Canonical Scroller Standard v2.1 compliance. Fits within the visible feed viewport without internal vertical scrolling.
- Live 6-Tile Queue Summary: Instant scannability across Unclaimed, Mine, Teammates, Suggested, Escalated, and Resolved items.
- Team Presence Tracking: Real-time detection of active moderators and high-level workload indicators (e.g. "u/modA — reviewing 2 items").
- Expanded Dashboard: Full tabbed interface featuring queue filtering, search, multi-item batch operations, workload balance, and audit activity streams.
- Select multiple queue items for bulk claim, release, suggest, handoff, note, or escalation.
- Automated pre-flight check detects items already claimed by teammates and skips them with clear conflict reporting, guaranteeing safety across concurrent operations.
- Native Action Detection (`onModAction`)**: Automatically detects approve, remove, spam, and ban actions taken in Reddit's native interface, closes the corresponding coordination case, releases the lock, and logs the outcome.
- Discord & Slack Webhooks: Optional real-time alerts for urgent escalations, queue thresholds, or handoffs.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)
- http: External HTTP Fetch access [Domains: discord.com, hooks.slack.com]

## Triggers and Activation
### Menu Actions
- Mod Dispatch: Claim for review: Moderator menu action (Location: subreddit)
- Mod Dispatch: Release claim: Moderator menu action (Location: subreddit)
- Mod Dispatch: Suggest to another mod: Moderator menu action (Location: subreddit)
- Mod Dispatch: Hand off to another mod: Moderator menu action (Location: subreddit)
- Mod Dispatch: Add shared note: Moderator menu action (Location: subreddit)
- Mod Dispatch: Escalate: Moderator menu action (Location: subreddit)
- Mod Dispatch: Mark resolved: Moderator menu action (Location: subreddit)
- Mod Dispatch: View case status: Moderator menu action (Location: subreddit)
- Mod Dispatch: Dashboard: Moderator menu action (Location: subreddit)

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- Subreddit: Release Reason (select, default: -). Release Reason

## Automation Capabilities
- Submits Automated Comments: No — Does not submit automated comments.
- Attaches Removal Notes: No — Does not attach removal notes.
- Approves Content: Yes — Approves content.
- Removes or Filters Content: Yes — Removes or filters non-compliant submissions.
- Dispatches Modmail Alerts: No — Does not send modmail notifications.
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Key patterns: ModDispatch:AlertSystem, ModDispatch:Sweeper, node:http

## Setup and Usage
- Install App: Install Mod Dispatch on your subreddit via the Reddit Developer Portal.
- Open Dashboard: From your subreddit menu, select Mod Dispatch: Dashboard to initialize the pinned control center.
- Configure Team Rules: In the dashboard Settings tab, set your team claim timeout (default: 15 minutes) and designate senior moderators.
- Coordinate from the Queue: Open any post or comment menu in your native Reddit queue to claim, suggest, or add shared notes.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.2 — 2026-11-09
- Initial release of Mod Dispatch: shared ownership, atomic claims, suggestions, handoffs, and canonical scroller status dashboard.

0.1.2 — 2026-11-09
- Initial release of Mod Dispatch: shared ownership, atomic claims, suggestions, handoffs, and canonical scroller status dashboard.

0.1.1 — 2026-11-09
- Initial release of Mod Dispatch: shared ownership, atomic claims, suggestions, handoffs, and canonical scroller status dashboard.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/moddispatch/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/moddispatch/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/moddispatch)
- [Support](https://www.reddit.com/r/grantdb)