> **User Guide & Overview** | [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/ring-escape)

# Ring Escape

> **Infiltrate a Goa'uld Serpent Flagship, sabotage critical subsystems, and escape through the Ring Transporter before the clock runs out.**

**Ring Escape** is a high-fidelity real-time stealth-action arcade game engineered directly for the Reddit client. Designed for Stargate SG-1 fans and competitive gaming communities, players navigate multi-deck grid maps, avoid patrolling Serpent Guards, deploy tactical Zat'nik'tel stuns, and sabotage four ship subsystems to power the transport rings and escape.

### Key Highlights
- **7 Tactical Ship Decks**: Infiltrate increasingly secure decks from Forward Barracks to the Throne Deck Omega.
- **Real-Time Guard Stealth**: Evade Sentinel and Sweeper Serpent Guard patrols with dynamic line-of-sight and alert levels.
- **Authentic SGC Gameplay**: Deploy Zat'nik'tel stuns, avoid alarm corridors, and activate the Ring Transporter for extraction.
- **Automated Global Leaderboard**: Persistent Redis sorted set tracking top-10 speedrun times, personal bests, and player ranks.

---

## The 4-Step Mission Loop

1. **Launch Mission**: Enter expanded mode to deploy into the active Goa'uld ship deck.
2. **Sabotage Subsystems**: Locate and hold-arm charges on Command Relay, Shield Conduit, Engine Core, and Hangar Control.
3. **Zat Patrols**: Tactically disable approaching Serpent Guards with Zat stuns when stealth routes are blocked.
4. **Ring Transporter Extraction**: Reach the Ring Chamber once all 4 charges are armed to beam out and record your speedrun score.

---

## Quick Setup (60-Second Onboarding)

1. **Install**: Add **Ring Escape** to your subreddit via the Reddit App Directory.
2. **Launch Post**: Open the Mod Menu anywhere in your subreddit and select **"Create Ring Escape Post"**.
3. **Engage Community**: Members click **"Play Mission"** inline to launch the expanded gameplay canvas.
4. **Track Rivalries**: High scores and ranks update automatically on the post's live leaderboard.

---

## Core Capabilities

- **Fluid Mobile & Desktop Controls**: Smooth keyboard movement (WASD/Arrows) and touch D-pad with continuous hold-to-repeat support.
- **Anti-Cheat Run Validation**: Cryptographic run seeds, server-side duration verification, and deterministic score recalculation.
- **Seamless Deck Progression**: In-memory level transitions across all 7 decks without jarring iframe reloads.
- **Zero Moderator Overhead**: Fully automated score submission, personal best retention, and tie-breaking leaderboards.

---

## The Old Way vs. The Ring Escape Way

| Traditional Text Game / Quiz | The Ring Escape Way |
| :--- | :--- |
| Static images with comment-based commands | Real-time interactive 60fps canvas gameplay inside Reddit |
| Manual score calculation by moderators | Automatic server-validated score calculation in Redis |
| Clunky turn-based delays | Real-time guard AI patrols, alarm states, and stealth timing |
| Single-screen trivia | 7 progressive ship decks with speedrun ranking |

---

## Support

For questions, feedback, or bug reports, visit [r/grantdb](https://www.reddit.com/r/grantdb).
When reporting an issue, please include the deck number, device (desktop browser vs Reddit mobile app), and any error text.

---

## Legal

- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/ring-escape/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/ring-escape/PRIVACY.md)

---

*Built with ♥ for the Stargate SG-1 community on Reddit*

---
*Built for fun on Reddit*
