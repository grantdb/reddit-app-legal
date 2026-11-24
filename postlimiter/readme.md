> **User Guide & Overview** | [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/postlimiter)

# PostLimiter User Guide

PostLimiter helps subreddit moderators prevent flooding while keeping separate topics, games, apps, or categories active.

## Quick Setup (Zero-Config Auto-Topic Mode)

1. Open **Mod Tools > Installed Apps > PostLimiter**.
2. Under **Quick Setup**, configure:
   - **Enable PostLimiter**: On
   - **Quota Mode**:
     - **Auto-Detect Topic (Recommended)**: Works immediately with no subject list. Blocks repeat posts about the same topic or link while allowing unrelated topics (for example, posting *"hey I like this app"* twice is blocked, while posting *"this is a great fishing boat"* and then *"I like this sports car"* is allowed).
     - **Per-Flair Auto-Quota**: Gives every Reddit post flair its own independent limit without configuring flair names.
     - **Custom Subject Rules (Advanced)**: Enforces custom per-subject limits defined in **Advanced: Custom Subject Rules**.
   - **Who Does the Topic Limit Apply To?**: **Same User Only (Default)** or **All Users (Subreddit-Wide Topic Limit)**.
   - **Max Posts Per Topic / Subject**, **Rolling Time Window**, **Time Unit** (`Hours` / `Days`), **Action**, and **Topic Matching Sensitivity** (`Strict`, `Balanced`, `Broad`).
   - **Max Overall Posts Per User (0 = Unlimited)**: Optional hard cap on total posts per user across all topics within an overall rolling window (e.g. `3` posts per `24 Hours`).

## Per-Type Removal Messages & Placeholders

Under **User Messages & Comments (Per Removal Type)**, configure distinct removal reasons and user-facing messages for:

- **Too Many Overall Posts**: Shown when a user reaches **Max Overall Posts Per User** across any topics.
- **Duplicate / Similar Title**: Shown when a post matches an active post with an identical or near-identical title.
- **Same Topic / Same Link**: Shown when a post matches an active topic by shared keywords or same external link URL.
- **Subject / Flair Quota**: Shown in **Per-Flair** and **Custom Subject Rules** modes (per-subject overrides supported).

Supported placeholders: `{subject}`, `{matchedTitle}`, `{maxPosts}`, `{window}`, `{remainingTime}`, `{author}`, `{subreddit}`, `{rulesUrl}`.

## Multi-Subject Configuration Example (Custom Subject Mode)

```json
[
  {
    "name": "Game A",
    "slug": "game-a",
    "priority": 1,
    "flairs": ["Game A"],
    "css": ["game-a"],
    "prefixes": ["[Game A]"],
    "tags": ["[Game A]"],
    "max": 1,
    "window": 24,
    "unit": "hours",
    "action": "remove_comment"
  },
  {
    "name": "Game B",
    "slug": "game-b",
    "priority": 2,
    "flairs": ["Game B"],
    "prefixes": ["[Game B]"],
    "max": 3,
    "window": 7,
    "unit": "days",
    "action": "remove_comment"
  },
  {
    "name": "App X",
    "slug": "app-x",
    "priority": 3,
    "flairs": ["App X"],
    "prefixes": ["[App X]"],
    "max": 2,
    "window": 7,
    "unit": "days",
    "action": "report"
  }
]
```

### Overlapping Rules & Conflict Resolution

- **Strictest Rule Wins (Default)**: Lowest effective posting rate (`maxPosts / windowMs`), breaking ties by lowest `maxPosts`, longest window, then alphabetical slug.
- **First Matching Rule Wins**: Highest-priority subject (lowest `priority` number, or earliest in configuration order).
- **Apply All Matching Rules**: Checks every matched subject's quota; enforces on the strictest exceeded rule or counts the post in all matched subjects if all pass.
- **Designated Primary Subject Wins**: Applies `primaryConflictSubjectSlug` if matched; otherwise falls back to strictest.

## Moderator Action Guide

Open **Check PostLimiter Quotas** from the subreddit moderator menu:

- **View User Quotas & History**: Inspect active counts, rolling windows, expiration timers, matched rules, expired/excluded posts, and recent audit entries.
- **Manually Exclude / Restore a Post**: Enter a Post ID (`t3_...`), optional reason, and check confirmation.
- **Reset User Quota (Single Subject or All Subjects)**: Clear active quota slots for a user with confirmation.
- **Temporary & Permanent Exemptions**: Grant timed per-subject exemptions or add/remove permanent subreddit exemptions with confirmation.
- **Decision Logs, Metrics & Config Summary**: Review recent post decisions, operational counters, audit trail, validation errors, and copyable JSON.
- **PostLimiter: Test Rule Match**: Dry-run any sample title and flair against your live configuration.

## Troubleshooting

- **Test posts by a moderator are not blocked**: Toggle **Exempt Subreddit Moderators** OFF under **Exemptions** while testing, then re-enable it afterward.
- **Subject not matching expected posts**: Run **PostLimiter: Test Rule Match** from the subreddit menu to inspect matching results and validation errors.
- **User still blocked after deleting a post**: Ensure **Count Posts Deleted by Author** is OFF (default) under **Post Lifecycle Counting Policies**, or use **Check PostLimiter Quotas** to exclude/reset.
- **Settings size limit**: `additionalSubjectsJson` supports up to **16,384 bytes** and **50 subject rules**.

## Privacy & Data Retention

- All data is stored exclusively inside Reddit's subreddit-scoped Devvit Redis storage; no external databases or third-party services are used.
- Active quota records expire automatically after the configured rolling window plus a 24-hour grace period, and a bounded 6-hour scheduled cleanup job prunes expired sets without scanning the Redis keyspace.
- Decision logs, post history indexes, duplicate-title entries, and moderator audit logs are retained for at most 30 days. Temporary exemptions expire automatically at their configured duration.
