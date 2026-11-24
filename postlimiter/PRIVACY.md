# Privacy Policy — PostLimiter

**Effective Date:** 2026-11-23

PostLimiter processes only the minimal Reddit post, moderation lifecycle, and account metadata required to enforce subreddit-configured rolling post quotas.

## 1. Data Collected

When PostLimiter is installed on a subreddit, it stores the following operational data inside Reddit's Devvit Redis storage scoped exclusively to that subreddit:

- Post ID, title, normalized title, matched subject/rule metadata, permalink, and lifecycle status (active, deleted, removed, spam, approved, or manually excluded)
- Author ID and username
- UTC creation and expiration timestamps and quota decision outcomes
- Moderator-managed temporary or permanent user exemptions
- Moderator action audit logs (moderator username, action, target username, subject, timestamp, and optional reason)
- Aggregate subreddit operational counters (evaluated, allowed, removed, reported, exempt, lifecycle updates)

## 2. Data Retention

- Active quota tracking records expire automatically after the configured rolling time window plus a short grace period and are pruned by a recurring scheduled cleanup job.
- Decision logs, duplicate-title index entries, and moderator audit logs expire automatically after 30 days.
- Temporary user exemptions expire automatically at their configured duration.
- No data is exported to external databases or third-party services.

## 3. Contact & Support

For privacy inquiries, contact the developer via [r/grantdb](https://www.reddit.com/r/grantdb).
