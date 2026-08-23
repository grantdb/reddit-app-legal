> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/sgteam-dispatch)

# SG Team Dispatch

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Gaming](https://img.shields.io/badge/Category-Interactive-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Game-8A2BE2?style=for-the-badge)

**SG Team Dispatch** is a replayable Stargate SG-1 inspired tactical mission command game engineered directly for Reddit custom posts. Commanders assemble specialized SG team rosters, manage offworld resources, and navigate multi-stage tactical encounters against Goa'uld, Replicator, and environmental threats.

## Key Features

- **Tactical SG Team Roster Selection**: Assemble specialized 4-member SG teams (Commander, Archaeologist, Engineer, Heavy Specialist, Tactical Specialist) with unique stat bonuses and role synergies.
- **Dynamic Offworld Encounters**: Multi-phase tactical missions (Opener, Mid-Game, Extraction) with branching risk choices influenced by biome, threat levels, and team role perks.
- **Resource & Threat Status Management**: Balance team Health, Time, Intel, Morale, and Goa'uld Alert meters to ensure mission success and safe gate extraction.
- **Daily Seeded Operations & Random Runs**: Play canonical daily offworld missions shared deterministically across the subreddit or command procedurally generated random operations.
- **Server-Authoritative State Engine**: All encounter options, decision tracking, resource state mutations, score evaluations, and ending tier determinations are computed strictly on the server.
- **Redis Leaderboards & Tie-Handling**: Subreddit all-time and daily command leaderboards with score preservation (no lower-score overwrites) and high-precision timestamp tie-breaking.

## How It Works

1. A moderator launches a new **SG Team Dispatch** post directly from the subreddit Mod Menu.
2. Players open the post to choose between a **Random Mission** or **Daily Operation**.
3. Commanders configure their 4-member SG team roster based on mission biome and threat analysis.
4. Commanders evaluate tactical choices across 3 encounter phases, balancing risk levels against team perks and resource constraints.
5. On mission completion or team evacuation, the server tallies final score breakdowns, assigns ending mission tiers, and updates subreddit leaderboards.

## Setup & Configuration

1. **Install**: Add **SG Team Dispatch** to your subreddit via the Devvit platform.
2. **Post Creation**: Open the Mod Menu on your subreddit and select "Create SG Team Dispatch Post".
3. **Play & Compete**: Commanders interact with the mission control canvas directly inside Reddit on mobile or desktop.

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

## Legal

This application is subject to standard legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/stargate-trivia/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/stargate-trivia/PRIVACY.md)

---
*Built for fun on Reddit*
