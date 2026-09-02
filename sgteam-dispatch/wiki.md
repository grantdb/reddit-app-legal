# SG Team Dispatch

Category: Interactive  
Version: v0.0.5  
Visibility: Unlisted  
Summary: Replayable Stargate SG-1 inspired tactical mission command game.

## Overview
Replayable Stargate SG-1 inspired tactical mission command game.

## Key Features
- Tactical SG Team Roster Selection: Assemble specialized 4-member SG teams (Commander, Archaeologist, Engineer, Heavy Specialist, Tactical Specialist) with unique stat bonuses and role synergies.
- Dynamic Offworld Encounters: Multi-phase tactical missions (Opener, Mid-Game, Extraction) with branching risk choices influenced by biome, threat levels, and team role perks.
- Resource & Threat Status Management: Balance team Health, Time, Intel, Morale, and Goa'uld Alert meters to ensure mission success and safe gate extraction.
- Daily Seeded Operations & Random Runs: Play canonical daily offworld missions shared deterministically across the subreddit or command procedurally generated random operations.
- Server-Authoritative State Engine: All encounter options, decision tracking, resource state mutations, score evaluations, and ending tier determinations are computed strictly on the server.
- Redis Leaderboards & Tie-Handling: Subreddit all-time and daily command leaderboards with score preservation (no lower-score overwrites) and high-precision timestamp tie-breaking.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- Not documented yet.

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- No custom app settings.

## Automation Capabilities
- Submits Automated Comments: No — Does not submit automated comments.
- Attaches Removal Notes: No — Does not attach removal notes.
- Approves Content: No — Does not approve content.
- Removes or Filters Content: Yes — Removes or filters non-compliant submissions.
- Dispatches Modmail Alerts: No — Does not send modmail notifications.
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Hashes (structured records & alias indices)
- Sorted Sets (time-series audit logs)
- Key patterns: node:http, sgtd:daily

## Setup and Usage
- Install: Add SG Team Dispatch to your subreddit via the Devvit platform.
- Post Creation: Open the Mod Menu on your subreddit and select "Create SG Team Dispatch Post".
- Play & Compete: Commanders interact with the mission control canvas directly inside Reddit on mobile or desktop.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.5 — 2026-09-02
- Standard fleet synchronization and maintenance.

0.0.4 — 2026-08-15
- Standard fleet synchronization and maintenance.

0.0.3 — 2026-07-27
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/sgteam-dispatch/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/sgteam-dispatch/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/sgteam-dispatch)
- [Support](https://www.reddit.com/r/grantdb)