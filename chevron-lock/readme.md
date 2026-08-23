> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/chevron-lock)

# Chevron Lock

![Reddit](https://img.shields.io/badge/Platform-Reddit%20Devvit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Category](https://img.shields.io/badge/Category-Interactive-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Game-8A2BE2?style=for-the-badge)

Operating an unstable SGC dialing console, players must identify, repair, and reorder gate address sequences under strict time pressure before gate system collapse. **Chevron Lock** brings an authentic Stargate dialing puzzle experience directly into Reddit feeds.

## Interactive Features

- **Dynamic Dialing Engine**: Encode destination glyphs plus the Point of Origin (Alpha Origin) under strict time pressure across gate sequences scaling from 3 to 7 chevrons.
- **3 Dynamic Round Types**:
  - **Recall**: Memorize a valid gate address during a brief preview window, then reconstruct it from memory.
  - **Repair**: Detect corrupted DHD chevron slots (`?`) and substitute them with correct glyphs from the DHD pool.
  - **Reorder**: Observe a memory preview, then swap scrambled chevron slots back into canonical sequence before time expires.
- **7-Round Escalating Run**: Smooth 3-round onboarding ramp (3 to 4 chevrons, 0 decoys) that scales up to a full 7-chevron Master Gate Lock in Round 7.
- **Daily Seeded Challenge**: A canonical daily address sequence shared deterministically across all players on the same UTC day.
- **Server-Authoritative Engine**: All scoring, sequence validation, timing checks, stability penalties, and leaderboard writes are computed strictly on the server.
- **Redis Leaderboards & Tie-Handling**: Subreddit all-time and daily sorted sets with score preservation (no lower-score overwrites) and high-precision timestamp tie-breaking.
- **SGC Dialing Console UI**: Dark graphite aesthetics, glowing teal chevrons, telemetry readouts, stability bars, and amber/red alert pulses.

## Gameplay Mechanics & Controls

- **Console Controls**:
  - **CLEAR**: Reset all slot selections or revert scrambled arrangements for the current round.
  - **HINT (-15 Pts)**: Reveal the correct glyph for a corrupted slot or position with a score penalty.
  - **LOCK CHEVRONS**: Transmit the encoded sequence to the gate for verification.
- **HUD Telemetry Readouts**:
  - **Round Counter**: Displays current round progress (e.g. `1/7`).
  - **Stability Indicator**: Represents remaining DHD stability charges (starts at 3 units; losing all stability collapses the gate).
  - **Timer**: Active countdown per round with visual warning pulses when under 3 seconds.
  - **Streak & Score**: Live tracking of consecutive successful locks and running score.

## Install / Use

1. Deploy and install the **Chevron Lock** app on your subreddit.
2. Open the subreddit post creation menu or moderator actions.
3. Select **Create Chevron Lock Post** to spawn an interactive dialing console post for your community.

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/chevron-lock/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/chevron-lock/PRIVACY.md)

---
*Built for fun on Reddit*
