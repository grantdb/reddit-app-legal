> **User Guide & Overview** | [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/domain-guard)

# DomainGuard

> **High-precision URL and domain moderation engine with rule-based filtering, post-edit auto-recheck, and moderator queue protection.**

DomainGuard inspects links and domain mentions across submissions and comments, enforces allowlist or blocklist policies with dry-run simulation support, and tracks filtered posts for automatic re-approval when authors remove offending URLs.

---

## At a Glance

- **Allowlist & Blocklist Rule Engine**: Match domains across post URLs, body links, or both with subdomain controls, risk-score thresholds, and moderator exemptions.
- **Auto-Recheck & Clean Auto-Approval**: Track filtered submissions and automatically re-evaluate on post edits or scheduled rechecks, approving and unlocking clean posts while permanently protecting approved items from being marked as spam.
- **Control Center & Dry-Run Mode**: Manage rules, inspect audit logs, test payloads in the Test Console, and simulate actions safely via throttled Modmail alerts before enforcing.
- **Idempotent & Moderator-Safe**: Deduplicates concurrent create/submit triggers and tracks moderator approvals in Redis so approved posts are never re-filtered or marked as spam.

---

## How It Works: The 4-Step Operational Pipeline

### 01 · Configure Rules & Mode

> **Launch the DomainGuard Dashboard**
> - Moderators open **GuardHub: DomainGuard Dashboard** from the subreddit menu (`...`) to create prioritized allowlist or blocklist rules.
> - Start in **Dry Run** mode to log matches and send throttled Modmail previews, or switch to **Enforce** mode for live moderation.

---

### 02 · Inspect Submissions & Comments

> **Tiered Domain Extraction & Delta Baseline**
> - On `onPostCreate`, `onPostSubmit`, `onCommentCreate`, and `onCommentSubmit`, DomainGuard extracts explicit URLs and naked domains while skipping exempt domains.
> - Previously approved items use a stored domain baseline so edits are only checked against newly introduced domains, and approved posts are never marked as spam.

---

### 03 · Enforce & Track Filtered Posts

> **Filter, Notify & Queue for Auto-Recheck**
> - Matching items execute the configured rule action (`filter`, `remove`, `spam`, `report`, or `log`), optionally post a removal notice, and record a ModNote.
> - Filtered submissions are queued in the Control Center with a configurable grace period for author edits.

---

### 04 · Auto-Recheck & Moderator Approval

> **Clean Recovery & Permanent Spam Protection**
> - When an author edits a filtered post to remove the offending URL (`onPostUpdate` or scheduled recheck), DomainGuard auto-approves the post, removes its notice comment, unlocks it, and registers its clean domain baseline.
> - Manual approvals via Reddit or the Control Center Filtered Queue immediately clear the queue entry and protect the post against future spam marking.

---

## Quick Setup

1. **Install**: Add **DomainGuard** to your subreddit via the Reddit Developer portal.
2. **Open Dashboard**: From your subreddit menu (`...`), select **GuardHub: DomainGuard Dashboard** and add your allowlist/blocklist rules.
3. **Verify & Enforce**: Test rules in the built-in Test Console or Dry Run mode, then switch to **Enforce** mode.

---

## Support

> **Need help, found a bug, or have a feature request?**
> Post in **[https://www.reddit.com/r/grantdb](https://www.reddit.com/r/grantdb)** with the app name (`domain-guard`), what you expected, what happened, and any error text or screenshots.
>
> - **Full User Guide**: [https://www.reddit.com/r/grantdb/wiki/domain-guard/](https://www.reddit.com/r/grantdb/wiki/domain-guard/)
> - **Technical Reference & Settings Spec**: [https://www.reddit.com/r/grantdb/wiki/index/all-apps/domain-guard/](https://www.reddit.com/r/grantdb/wiki/index/all-apps/domain-guard/)

---

## Legal

- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/domain-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/domain-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
