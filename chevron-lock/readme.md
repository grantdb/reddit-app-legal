# Chevron Lock

![Reddit](https://img.shields.io/badge/Platform-Reddit%20Devvit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Category](https://img.shields.io/badge/Category-Interactive-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Game-8A2BE2?style=for-the-badge)

> **Operate an unstable SGC dialing console and lock destination chevrons before gate collapse.**

Players identify, repair, and reorder authentic Stargate gate address sequences under strict time pressure directly within Reddit custom posts. Compete on subreddit all-time and daily seed leaderboards with server-authoritative state security.

### Key Highlights
- **7-Round Escalating Difficulty**: Onboarding starts at 3 chevrons and ramps smoothly to the full 7-chevron Master Gate Lock.
- **3 Dynamic Puzzle Modes**: Test memory and reflexes across Recall, Repair (corrupted DHD slots), and Reorder (scrambled glyph sequences).
- **Subreddit Leaderboards**: Server-authoritative scoring with zero client trust, monotonic personal best tracking, and deterministic daily seeds.
- **Zero Scroll Traps**: Native inline preview with 8px gesture drag guard and seamless high-contrast SGC tactical console.

## How It Works

### The 5-Step Dialing Lifecycle
1. **Mission Briefing**: Players inspect the dialing computer in an inline Reddit post and select Procedural Dial or Daily Challenge.
2. **Telemetry Calibration**: The console presents round parameters (sequence length, time limit, and puzzle archetype).
3. **Memory & Analysis**: In Recall rounds, players memorize the active sequence; in Repair rounds, they locate corrupted slots; in Reorder rounds, they analyze scrambled glyphs.
4. **Encoding & Transmission**: Operators select glyphs from the DHD pool, use optional hints (-15 pts), and transmit the sequence to the Stargate.
5. **Debrief & Leaderboards**: Upon completing all 7 rounds or suffering a stability collapse, the server calculates score breakdowns and records personal best rankings.

## Quick Setup (60-Second Onboarding)

1. **Install**: Add **Chevron Lock** to your subreddit via the Devvit developer platform.
2. **Launch Post**: Open the subreddit Moderator Menu and select **"Create Chevron Lock Post"**.
3. **Configure Options**: The post embeds an interactive dialing console directly in your community feed.
4. **Deploy & Compete**: Community members dial gate addresses, maintain stability, and compete for top operator rankings.

## Core Capabilities

### 3 Dynamic Dialing Modes
- **Recall**: Memorize an active gate address during a brief preview window, then reconstruct it from memory before the timer expires.
- **Repair**: Identify corrupted DHD chevron slots (`?`) and substitute them with the correct glyph from the offworld symbol pool.
- **Reorder**: Analyze scrambled chevron positions and swap slots into their canonical dialing sequence under time pressure.

### SGC Dialing Console Controls
- **CLEAR**: Reset all slot selections or revert scrambled arrangements for the current round.
- **HINT (-15 Pts)**: Reveal the correct glyph for a corrupted slot or position with a modest score penalty.
- **LOCK CHEVRONS**: Transmit the encoded sequence to the gate for server verification.

### Server-Authoritative State Engine
Every sequence validation, timing grace period, stability reduction, and score calculation is resolved inside Devvit server endpoints. Player choices cannot be spoofed, and high-precision composite scores are stored in Redis sorted sets.

## The Old Way vs. The Chevron Lock Way

| Feature | Old Text Puzzles | The Chevron Lock Way |
| :--- | :--- | :--- |
| **Experience** | Static comment-based trivia | Interactive SGC dialing computer console |
| **Mechanics** | Passive multiple choice | 3 dynamic puzzle types with real-time countdowns |
| **Competition** | Manual comment tallying | Real-time Redis leaderboards & daily seeded runs |
| **Security** | Easily spoofed answers | Server-authoritative state resolution & zero client trust |

## Privacy & Fair Play

Chevron Lock stores only standard Reddit usernames, anonymized user IDs, and mission scores in subreddit-scoped Redis storage. No personal data, tracking cookies, or external server calls are utilized. All gameplay is purely server-verified for community fair play.

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/chevron-lock/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/chevron-lock/PRIVACY.md)

---
*Built for fun on Reddit*
