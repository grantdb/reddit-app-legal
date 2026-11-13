> **User Guide & Overview** | [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/queueclue)

# QueueClue

> **Find the available source and reason behind a queue item.**

QueueClue gives moderators a clear, read-only explanation of why a post or comment was filtered into Reddit's Needs Review queue. Inspect confirmed removal categories, AutoModerator rule reasons, author context, and available moderation records directly on demand without leaving your queue or changing moderation states.

---

## At a Glance

- **Zero-Mutation Safety**: Operates strictly in read-only inspection mode with zero automated approvals, removals, or state mutations.
- **Unified Multi-Source Diagnosis**: Combines AutoModerator filter events, broker ModAction history, on-demand moderation log scans, native removal reasons, removal notices, and author context into a single chronological view.
- **Explicit Author & Account Context**: Surfaces account age, global and subreddit karma, email verification, prior community mod notes, and explicit status when an author account is deleted, suspended, or unavailable.
- **Preserved Queue Context**: Opens a native explanation popover modal so moderators review context and close it without losing their queue position.

---

## How It Works: The 4-Step Operational Pipeline

### 01 · Trigger

> **On-Demand Queue Menu Invocation**
> - A moderator opens the moderator action menu on a post or comment in the Needs Review queue and selects **QueueClue: Why filtered?**.
> - Real-time `onAutomoderatorFilterPost`, `onAutomoderatorFilterComment`, and `onModAction` triggers also capture exact rule reasons and action chronology in bounded Redis storage (30-day TTL).

---

### 02 · Authorize & Verify

> **Moderator & Subreddit Boundary Check**
> - QueueClue verifies the invoking user's active moderator permissions server-side before inspecting any record.
> - Confirms the target post or comment belongs to the current subreddit to prevent cross-subreddit leakage.

---

### 03 · Inspect & Classify

> **Ground-Truth Evidence Evaluation**
> - Evaluates captured AutoModerator events, moderation log entries, native removal reasons, and correlated removal notices without overstating uncertain signals.
> - Fetches author context and community mod note history on demand, explicitly reporting deleted, suspended, or 404/unavailable accounts.

---

### 04 · Present

> **Native Popover Summary**
> - Opens a read-only explanation modal showing the verified filtering source, plain-English platform category (`automod_filtered`, `reddit`, `anti_evil_ops`, `copyright_takedown`), relative and subreddit-local timestamps, and author context.
> - Closing the modal returns the moderator directly to their exact queue position.

---

## Quick Setup

1. **Install**: Add **QueueClue** to your subreddit from the Reddit App Directory.
2. **Open Queue**: Navigate to your subreddit's **Needs Review** queue in desktop Reddit Mod Tools.
3. **Inspect Item**: Open the item's moderator action menu and click **QueueClue: Why filtered?** to view the diagnostic summary.

---

## Support

> **Community Support**: Need help, want to report a bug, or have a feature request? Post in [https://www.reddit.com/r/grantdb](https://www.reddit.com/r/grantdb) with the app name (`queueclue`), expected behavior, actual behavior, and any error details.

- **Full User Guide**: [https://www.reddit.com/r/grantdb/wiki/queueclue/](https://www.reddit.com/r/grantdb/wiki/queueclue/)
- **Technical Reference & Settings Spec**: [https://www.reddit.com/r/grantdb/wiki/index/all-apps/queueclue/](https://www.reddit.com/r/grantdb/wiki/index/all-apps/queueclue/)

---

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/queueclue/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/queueclue/PRIVACY.md)

---
*Built for Reddit's moderator community.*
