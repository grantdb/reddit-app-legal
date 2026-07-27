# SG Team Dispatch

**SG Team Dispatch** (`sgteam-dispatch`) is a replayable Stargate SG-1 inspired tactical mission command game built as a Reddit Devvit custom post app.

## Overview
Players act as SGC Mission Commanders:
1. Select a 4-person SG team loadout from 8 distinct specialist roles.
2. Accept a procedurally generated or daily offworld mission briefing.
3. Resolve 5 branching tactical encounters (opener, 3 mid-encounter events, and extraction).
4. Balance 5 key operational stats (Health, Time, Intel, Morale, Alert).
5. Extract through the Stargate to receive a server-validated debrief report and leaderboard ranking.

## Features
- **Deterministic Seeded Missions**: Generate consistent missions per seed or play the daily subreddit challenge.
- **8 Unique Roles**: Team Leader, Scientist, Linguist, Medic, Heavy, Scout, Engineer, Jaffa Ally.
- **5 Mission Archetypes & Biomes**: Recon, Rescue, Artifact Recovery, Sabotage, Diplomatic Contact.
- **Server-Authoritative Anti-Cheat**: All choice consequences, resource calculations, and leaderboard writes are executed server-side.
- **Redis Leaderboards**: Subreddit All-Time and Daily Challenge sorted sets keyed by stable User IDs with tie-handling.
- **SGC Tactical UI**: Dark command room aesthetics with teal/amber indicators, warning chips, scanlines, and debrief paperwork visuals.

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

## License
BSD-3-Clause

*Built for fun on Reddit*
