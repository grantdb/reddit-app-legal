> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/reference-reply-bot)

# Reference Reply Bot (`r/grantdb`)

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Support-blue?style=for-the-badge)

**Reference Reply Bot** is a post-only support intake and reference utility built for **r/grantdb**. It monitors new support posts, identifies support intent and app references using deterministic heuristic scoring, and posts concise, non-conversational troubleshooting guidance and documentation links.

---

## Key Features & Production Design

- **Post-Only Support Focus**: Listens strictly to `onPostSubmit` events to provide immediate triage and reference replies on new support submissions in `r/grantdb`.
- **Confidence-Based Reply Shaping**: Categorizes matched results into confidence bands (`high`, `medium`, `low`) to dynamically tailor response length, section visibility, and diagnostic blocks.
- **Likely Cause & Safe-First Actions**: Surfaces diagnostic `Likely cause` blocks for high/medium confidence matches and ranks safe, non-disruptive troubleshooting actions first (settings check → Mod Menu test → console logs).
- **Semantic Intent Deduplication**: Prunes near-duplicate troubleshooting bullets by intent signature (`dedupeBulletsByIntent`) to keep replies compact and focused.
- **Atomic Concurrency Lock**: Uses Redis `watch` and multi-exec transactions (`rrb:processing:<postId>`) to acquire a 30-second processing lock, preventing race conditions when event triggers fire concurrently.
- **Post-Execution Replied Marker**: The permanent deduplication marker (`rrb:replied:<postId>`) is written **only after** `submitComment` succeeds. If commenting fails, the lock is released in a `finally` block so the post can be retried safely.
- **Structured Redis App Knowledge**: App documentation records are stored in `rrb:apps` and `rrb:aliases` Redis hashes for easy bulk ingestion of fleet README files.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/reference-reply-bot-flowchart.png)

```
[ New Post Submission Received ]
               │
               ▼
[ Check Permanent Replied Marker (rrb:replied:<postId>) ] ──(Replied)──► [ Skip ]
               │
               ▼
[ Acquire Atomic Processing Lock (rrb:processing:<postId>) ] ──(Locked)──► [ Skip ]
               │
               ▼
[ Support Intent & App Alias Scoring ]
               │
               ▼
[ Intake Completeness Analysis ] ──(No App Match)──► [ Missing App Mode Reply ]
               │
               ▼ (App Matched)
[ Completeness >= Threshold? ] ──(No)──► [ Hybrid Mode Reply ]
               │
               ▼ (Yes)
[ Normal Reference Reply ] ──(On Success)──► [ Write Replied Marker & User Cooldown ]
               │
               └───────(Always)──► [ Release Lock via finally Block ]
```

---

## App Settings

Configure via **Mod Tools -> App Settings** in `r/grantdb`:

| Setting Name | Type | Default | Description |
|---|---|---|---|
| `enabled` | Boolean | `true` | Master toggle to enable or pause support bot monitoring. |
| `welcomeRepliesEnabled` | Boolean | `true` | Auto-reply to new support posts with reference guidance. |
| `minConfidence` | Number | `60` | Post score threshold (0-100) required to reply. |
| `completenessThreshold` | Number | `0.60` | Threshold below which matched app replies append a missing details section (hybrid mode). |
| `replyCooldownMinutes` | Number | `15` | Window before replying to the same user again. |
| `supportFlairs` | String | `Support, Bug, Help, Question` | Comma-separated post flairs to monitor. Blank = all posts. |
| `maxLinksPerReply` | Number | `2` | Maximum documentation links per automated reply. |
| `debugLogging` | Boolean | `false` | Log scoring details and lock statuses to the console. |

---

## Seeding & Testing Data

1. Install the app on `r/grantdb` or your dev subreddit.
2. Go to **Mod Tools -> Subreddit Menu -> click "GrantDB Support: Seed App Knowledge Database"**.
3. Redis is populated with live knowledge dynamically fetched from `r/grantdb/wiki/bot_knowledge` (or bundled fallback if missing).
4. Content updates can be re-seeded instantly without needing an app rebuild or deployment.
5. To reset data, click **"GrantDB Support: Clear Knowledge Database"**.

---

## Redis Data Taxonomy

- `rrb:apps` *(Hash)*: Stores JSON stringified `AppKnowledge` objects keyed by `appId`.
- `rrb:aliases` *(Hash)*: Maps lowercase app aliases to `appId`.
- `rrb:processing:<postId>` *(String, 30s TTL)*: Atomic concurrency processing lock acquired via `watch`.
- `rrb:replied:<postId>` *(String, 7-day TTL)*: Permanent deduplication marker written upon comment success.
- `rrb:cooldown:<authorId>` *(String, N-min TTL)*: Per-user cooldown timer.

---

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

---

## Legal

- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/reference-reply-bot/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/reference-reply-bot/PRIVACY.md)

---
*Built for Reddit's moderator community.*
