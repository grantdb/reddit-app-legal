# Gate Defender

Category: Interactive  
Version: v0.0.102  
Visibility: Public  
Summary: Community security gatekeeper. React Webview-based entry validation.

## Overview
Community security gatekeeper. React Webview-based entry validation.

## Key Features
- High-Velocity Survival Mechanics: Fast-paced, responsive arcade gameplay with adaptive turret aiming, recoil physics, and bullet collision detection.
- Iris Barrier Defense Dome: An energy shield dome covering the gate that absorbs up to 12 incoming plasma blasts and vaporizes invaders that ram the gate perimeter.
- Mobile Defensive Flank Formation: On mobile viewports, the perimeter automatically structures into a symmetric 6-ruin defensive arc flanking the turret.
- Kill-Streak Overcharge & Bonus Shields: In desktop/fullscreen mode, maintaining a 10-kill streak without taking damage rewards bonus Iris Barrier integrity (+5 hits), reserve ammo (+60), and personal turret shield repair.
- Persistent Global Leaderboards: Real-time "Top 10" ranking system embedded directly in the post to encourage community rivalry and tournament events.
- Adaptive Cross-Device Controls: Seamless responsive viewport re-anchoring across desktop, tablet, and mobile layouts with unified Pointer Events and touch controls.
- Interactive Onboarding: Pre-game splash screen providing rapid tutorial instructions and one-click launch directly into expanded mode.
- Moderator-Initiated Launch: Simple one-click deployment via the Subreddit Moderator Menu to schedule gaming events or community threads.

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
- Sorted Sets (time-series audit logs)
- Key patterns: node:http, node:events

## Setup and Usage
- Install: Add Gate Defender to your subreddit via the App Directory.
- App Settings: (Optional) Use the subreddit's App Settings to tweak gameplay difficulty multipliers if your community wants a harder challenge.
- Usage: To start a community event, simply open the Mod Menu anywhere in your subreddit and select the "Launch Gate Defender" action to spawn a new game post.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.102 — 2026-10-03
- Viewport Resize & Firing Fix: Resolved bug where switching from desktop to mobile viewport in the UI Simulator or rotating devices caused the turret and world coordinates to stay outside the canvas boundaries, immediately culling all fired projectiles.
- Unified Pointer Engine: Migrated touch and mouse handlers to unified Pointer Events with `setPointerCapture`, `touch-action: none` on game canvas, and proper release cleanup on `blur` and `visibilitychange`.
- Iris Barrier Defense Dome: Introduced planetary shield absorbing up to 12 plasma blasts and vaporizing invading attackers on collision.
- Mobile Flank Formation: Standardized mobile layout to max 6 ancient ruins placed in a balanced defensive arc flanking the gate turret.
- Desktop Kill-Streak Bonus: Enabled 10-kill streak rewards on desktop/fullscreen granting bonus Iris Barrier integrity (+5 hits), extra ammo (+60), and personal turret shield repair, with 30% ammo drop probability.
- Plausibility Score Check: Raised server-side score plausibility limit from 250 to 2500 pts/sec after runtime audit revealed genuine high-score runs were being falsely rejected.
- HUD & Status Feedback: Stacked mobile HUD downward beneath score display to prevent touch-control overlap, and added real-time score transmission status feedback on game-over screen.

0.0.101 — 2026-09-21
- Standard fleet synchronization and maintenance.

0.0.100 — 2026-09-15
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/gate-defender/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/gate-defender/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/gate-defender)
- [Support](https://www.reddit.com/r/grantdb)