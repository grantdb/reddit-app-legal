> **User Guide & Overview** | [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/postlimiter)

# PostLimiter

> **Independent per-user, per-subject rolling post quotas that stop flooding without silencing active community categories.**

PostLimiter is a configurable Reddit moderation app built on Devvit. It lets subreddit moderators define separate posting limits and rolling time windows for each game, app, support topic, or category so a user who hits their limit in one subject can still post freely in unrelated subjects.

## At a Glance

- **Independent Per-Subject Quotas**: Configure distinct limits per category (for example, Game A at 1 post per 24 hours, Game B at 3 posts per 7 days, and App X at 2 posts per 7 days) without cross-blocking unrelated subjects.
- **Flexible Subject Matching & Conflict Resolution**: Map posts via exact or case-insensitive flair text, flair CSS class, title prefix, bracketed title tags (`[Game A]`), or optional safe regex (off by default). Choose how overlapping rules resolve: strictest rule, first match, apply all, or designated primary subject.
- **Reliable Post Lifecycle Handling**: Automatically updates active quotas when posts are deleted by authors, removed by moderators or AutoModerator, marked as spam, approved after removal, edited, or reflaired.
- **Full Moderator Operations & Observability**: Inspect active and historical posts, exclude or restore posts, reset quotas, grant temporary or permanent exemptions with confirmation and audit logs, test rule matches in dry-run mode, and track operational metrics.

## How It Works: The 6-Step Operational Pipeline

### 01 · Atomic Deduplication & Exemption Check

> **Guarantees every submission is evaluated at most once**
> - Acquires an atomic Redis NX lock (`quota:lock:{subredditId}:{postId}`) shared between `PostSubmit` (primary) and `PostCreate` (fallback) and tracks prevented duplicates in operational metrics.
> - Safely ignores deleted or already-removed posts and honors global, per-subject, temporary, and moderator-managed permanent exemptions.

---

### 02 · Subject Matching & Conflict Resolution

> **Maps the post to its target category without hardcoded names**
> - Evaluates configured subjects in priority order against flair text (exact or case-insensitive), flair CSS class, title prefix, title tags, and optional validated regex patterns.
> - Resolves overlapping subject matches using the configured strategy (`strictest`, `first_match`, `apply_all`, or `primary_subject`) and logs every matched rule.
> - Applies the configured fallback behavior (`allow`, `default_quota`, `remove`, or `report`) when no subject matches.

---

### 03 · Rolling Window Evaluation & Optional Duplicate-Title Check

> **Checks only active, non-expired, counted posts in scan-free Redis sorted sets**
> - Queries `quota:active:{subredditId}:{subjectId}:{userId}` without scanning Redis keys and opportunistically prunes expired entries.
> - Stores normalized titles for all tracked posts; duplicate-title enforcement is **disabled by default** and scoped to `same_user` so different users posting similar titles are never blocked unless moderators deliberately opt in.

---

### 04 · Enforcement & Clear User Communication

> **Never silently removes a post without a clear, configurable reason**
> - Executes the configured action (`remove`, `report`, `remove_comment`, `remove_modmail`, `report_comment`, `leave_comment`, or `leave_modmail`).
> - Supports distinguished comment modes (`always`, `first_violation_only`, `subject_only`, `never`) and optional subreddit rules/wiki links while clearly stating the subject, limit, window, wait time, and confirming other subjects are unaffected.

---

### 05 · Lifecycle Synchronization & Scheduled Cleanup

> **Keeps active quotas accurate after edits, flair changes, removals, and deletions**
> - Responds to `PostDelete`, `PostUpdate`, `PostFlairUpdate`, and `ModAction` (`removelink`, `spamlink`, `approvelink`) using configurable counting policies.
> - Runs a recurring scan-free cleanup job every 6 hours to purge expired active sets, old title records, and aged audit entries.

---

### 06 · Moderator Operations & Dry-Run Testing

> **Complete operational control with confirmation gates and audit logging**
> - **Check PostLimiter Quotas**: View active/expired posts, matched rules, exclusion reasons, decision logs, metrics, and copyable config JSON; exclude/restore posts, reset quotas, and manage temporary or permanent exemptions (all state-changing actions require explicit confirmation and write to the audit trail).
> - **PostLimiter: Test Rule Match**: Dry-run any sample title and flair to see which subject and quota rule would apply.

## Quick Setup

1. **Install PostLimiter** on your subreddit and open **Mod Tools -> Installed Apps -> PostLimiter**.
2. **Choose Your Mode in Quick Setup** (works immediately with zero subject lists):
   - **Auto-Detect Topic (Recommended — Default)**: Automatically limits repeat posts about the same topic (e.g. posting *"hey I like this app"* twice is blocked, while posting *"this is a great fishing boat"* and then *"I like this sports car"* is allowed). Choose **Same User Only** (default) or **All Users** (subreddit-wide).
   - **Per-Flair Auto-Quota**: Automatically gives every Reddit post flair its own independent limit without configuring flair names.
   - **Custom Subject Rules (Advanced)**: Define distinct per-category limits in **Advanced: Custom Subject Rules** (JSON or quick fields) if you want different limits for specific games, apps, or categories.
3. **Set Max Posts, Rolling Window, and Action** (e.g. `1` post per `24 Hours`, `Remove + Comment`) and save.

### Multi-Subject Configuration Example

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

When a single post matches more than one subject (for example, flair `Game B` and title tag `[Support]`):

- **Strictest Rule Wins (Default)**: Selects the subject with the lowest effective posting rate (`maxPosts / windowMs`), breaking ties by lowest `maxPosts`, longest window, then alphabetical slug.
- **First Matching Rule Wins**: Selects the highest-priority subject (lowest `priority` number, or earliest in configuration order).
- **Apply All Matching Rules**: Checks every matched subject's quota; if any matched subject is exceeded, enforces on the strictest violated rule, otherwise counts the post in all matched subjects.
- **Designated Primary Subject Wins**: Applies `primaryConflictSubjectSlug` if it is among the matched subjects; otherwise falls back to strictest.

### Duplicate-Title Foundation (Disabled by Default)

- Duplicate-title enforcement is **off by default** and must be deliberately enabled by moderators.
- Even when enabled, the default scope is **Same User Only**, so two different users posting similar titles (e.g. `"My App Update"`) are **not** blocked unless a moderator explicitly switches the scope to `same_subject` or `entire_subreddit`.

### Moderator Action Guide

Open **Check PostLimiter Quotas** from the subreddit moderator menu (moderator permissions are verified both by Reddit's menu gate and at runtime before execution):

- **View User Quotas & History**: Enter a username to inspect active counts, rolling windows, expiration timers, matched rules, expired/excluded posts, and recent audit entries.
- **Manually Exclude / Restore a Post**: Enter a Post ID (`t3_...`), optional reason, and check **Confirm Destructive / State-Changing Action** to remove or re-include a post in active quota counts.
- **Reset User Quota (Single Subject or All Subjects)**: Enter a username (and subject slug for single-subject reset), reason, and check confirmation to clear active quota slots.
- **Temporary & Permanent Exemptions**: Grant a timed per-subject exemption (in hours) or add/remove a permanent subreddit-wide exemption with confirmation.
- **Decision Logs, Metrics & Config Summary**: Inspect recent post decisions, operational counters, moderator audit trail, validation errors/warnings, and copyable compact JSON.
- **PostLimiter: Test Rule Match**: Dry-run any sample title and flair to verify which subject, matching method, and quota rule would apply without modifying any stored data.

Every state-changing moderator action writes an audit entry recording the moderator username, action, target user, subject, timestamp, and reason.

### Troubleshooting

- **Subject not matching expected posts**: Run **PostLimiter: Test Rule Match** from the subreddit menu to inspect which method matched and check for configuration validation errors.
- **User still blocked after deleting a post**: Verify **Count Posts Deleted by Author** is turned OFF (default) under **Post Lifecycle Counting Policies**, or use **Check PostLimiter Quotas -> Manually Exclude a Post / Reset User Quota**.
- **Regex rule not firing**: Confirm **Enable Optional Regex Title Matching** is enabled and check **View Configuration Summary** for unsafe-pattern validation errors (nested quantifiers and backreferences are rejected for safety).
- **Settings size limit**: `additionalSubjectsJson` supports up to **16,384 bytes** and **50 subject rules**; use compact keys (`flairs`, `css`, `prefixes`, `tags`, `max`, `window`, `unit`, `action`) for large rule sets.

### Privacy & Data Retention

- All data is stored exclusively inside Reddit's subreddit-scoped Devvit Redis storage; no external databases or third-party services are used.
- Active quota records expire automatically after the configured rolling window plus a 24-hour grace period, and a bounded 6-hour scheduled cleanup job prunes expired sets without scanning the Redis keyspace.
- Decision logs, post history indexes, duplicate-title entries, and moderator audit logs are retained for at most 30 days. Temporary exemptions expire automatically at their configured duration.

## Support

> **Official Support Community**: [https://www.reddit.com/r/grantdb](https://www.reddit.com/r/grantdb)

- **Full User Guide**: [https://www.reddit.com/r/grantdb/wiki/postlimiter/](https://www.reddit.com/r/grantdb/wiki/postlimiter/)
- **Technical Reference & Settings Spec**: [https://www.reddit.com/r/grantdb/wiki/index/all-apps/postlimiter/](https://www.reddit.com/r/grantdb/wiki/index/all-apps/postlimiter/)

## Legal

- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/postlimiter/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/postlimiter/PRIVACY.md)

---

*Moderation — PostLimiter*

---
*Built for Reddit's moderator community.*
