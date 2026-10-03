> **User Guide & Overview** | [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/sgteam-dispatch)

# SG Team Dispatch

> **Lead elite SG-1 tactical squads through offworld Stargate operations directly inside Reddit.**

Commanders assemble specialist rosters, balance vital offworld squad resources, and navigate multi-phase branching tactical encounters against Goa'uld and offworld hazards. Compete on subreddit all-time and daily seed leaderboards with server-authoritative state security.

### Key Highlights
- **Specialist Squad Synergy**: Assemble 4-member rosters across Commander, Archaeologist, Engineer, Heavy Specialist, and Tactical Specialist roles.
- **Dynamic Branching Missions**: 5 multi-tier encounter stages with risk-reward tactical decisions shaped by specialist perks.
- **Subreddit Leaderboards**: True server-authoritative scoring with zero client trust, monotonic personal best tracking, and daily seeded challenges.
- **Zero Scroll Traps**: Native inline preview with 8px gesture drag guard and seamless high-contrast tactical webview console.

## How It Works

### The 5-Step Mission Lifecycle
1. **Mission Briefing**: Commanders review offworld sector data in an inline Reddit post and select Procedural Dispatch or Daily SGC Operation.
2. **Squad Loadout**: Select 4 specialists whose unique stat bonuses and role perks provide tactical advantages in offworld scenarios.
3. **Offworld Exploration**: Progress through 5 encounter phases, balancing Health, Time, Intel, Morale, and Goa'uld Alert meters.
4. **Tactical Decisions**: Choose between aggressive, diplomatic, or technical solutions based on active squad composition.
5. **Debrief & Extraction**: Extract through the Stargate to receive a comprehensive scoring breakdown and lock in subreddit rankings.

## Quick Setup (60-Second Onboarding)

1. **Install**: Add **SG Team Dispatch** to your subreddit from the Reddit Developer portal or app directory.
2. **Launch Post**: Open the subreddit Moderator Menu and select **"Create SG Team Dispatch Post"**.
3. **Configure Options**: The post embeds an interactive tactical mission command console directly in your community feed.
4. **Deploy & Compete**: Subreddit members assemble squads, deploy offworld, and compete for top commander rankings.

## Core Capabilities

### Squad Composition & Role Perks
Assemble your dream team from 5 distinct SGC specializations. Archaeologists excel at Goa'uld artifact diplomacy, Engineers bypass Ancient defense grids, Heavy Specialists neutralize enemy patrols, Tactical Specialists minimize alarm escalation, and Commanders maintain squad morale in crisis situations.

### Dual Mission Modes
- **Procedural Dispatch**: Endless randomized offworld missions with dynamic biomes (Ancient Ruins, Goa'uld Stronghold, Alien Outpost).
- **Daily SGC Operation**: A synchronized, deterministic daily mission seed shared across all subreddit members for fair daily competition.

### Server-Authoritative State Engine
Every tactical choice, resource mutation, and score calculation is validated and resolved inside Devvit server endpoints. Player choices cannot be spoofed, and scores are verified server-side with atomic Redis sorted-set storage.

## The Old Way vs. The SG Team Dispatch Way

| Feature | Old Text Scenarios | The SG Team Dispatch Way |
| :--- | :--- | :--- |
| **Experience** | Passive static reading | Interactive SGC tactical command console |
| **Mechanics** | No resource constraints | 5 balancing meters (Health, Time, Intel, Morale, Alert) |
| **Competition** | Manual comment tallying | Real-time Redis leaderboards & daily seeded runs |
| **Security** | Easily spoofed claims | Server-authoritative state resolution & zero client trust |

## Privacy & Fair Play

SG Team Dispatch stores only standard Reddit usernames, anonymized user IDs, and mission scores in subreddit-scoped Redis storage. No personal data, tracking cookies, or external server calls are utilized. All gameplay is purely server-verified for community fair play.

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

## Legal

This application is subject to standard legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/sgteam-dispatch/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/sgteam-dispatch/PRIVACY.md)

---
*Built for fun on Reddit*
