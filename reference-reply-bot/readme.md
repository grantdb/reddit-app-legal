> **User Guide & Overview** | [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/reference-reply-bot)

# Reference Reply Bot

> **Automated support intake, reference guidance, and `fixed` resolution tracking for `r/grantdb`.**

Reference Reply Bot monitors new support posts in `r/grantdb`, scores app intent and intake completeness, posts tailored troubleshooting guidance with documentation links, and automatically updates post flair to `Fixed` when the author or a moderator replies `fixed`.

> **Documentation**: [Full User Guide](https://www.reddit.com/r/grantdb/wiki/reference-reply-bot/) | [Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/reference-reply-bot/)

---

## At a Glance

- **Support Intake & App Matching**: Detects support posts (`PostSubmit` / `PostCreate`), matches fleet app aliases from Redis (`rrb:apps`, `rrb:aliases`), and scores intake completeness.
- **Confidence-Shaped Replies**: Posts concise troubleshooting steps, likely causes, and wiki links while respecting per-user cooldowns and atomic Redis locks.
- **Automated `fixed` Resolution**: Listens on `CommentSubmit` for `fixed` replies from the post author or a moderator, updates the post flair to `Fixed`, and asks the user to share what solved the issue.
- **Moderator Hub Controls**: Includes a subreddit Moderator Hub (`Seed / Sync Knowledge Database`, `Clear My Testing Cooldown`, `Clear Knowledge Database`) and on-demand post analysis.

---

## How It Works: The 4-Step Operational Pipeline

### 01 · Support Post Intake & Deduplication
> **Filter, lock, and prevent duplicate replies on new posts**
> - Evaluates `PostSubmit` and `PostCreate` events against `supportFlairs` and `enabled` settings.
> - Acquires a 30-second Redis `watch` lock (`rrb:processing:<postId>`) and checks `rrb:replied:<postId>` and user cooldowns.

---

### 02 · Intent Scoring & Completeness Analysis
> **Identify the target app and missing diagnostic details**
> - Scores post title and body against the seeded Redis knowledge base (`bot_knowledge`).
> - Evaluates completeness against `completenessThreshold` to choose `normal`, `hybrid`, or `missing_app` reply mode.

---

### 03 · Reference Reply & Prompt Footer
> **Deliver actionable guidance and invite confirmation**
> - Posts troubleshooting steps and up to `maxLinksPerReply` documentation links.
> - Appends `resolutionFooterText` inviting the user to reply `fixed` once resolved.

---

### 04 · `fixed` Reply Detection & Flair Update
> **Close the loop when the issue is resolved**
> - Listens on `CommentSubmit` for exact `fixed` replies from the post author (OP) or a subreddit moderator.
> - Applies the `fixedFlairName` post flair template (`Fixed`) and replies asking the user to describe what fixed the issue.

---

## Quick Setup

1. **Install**: Add **Reference Reply Bot** to your subreddit and ensure a `Fixed` post flair template exists.
2. **Configure**: Open **Mod Tools > App Settings > Reference Reply Bot** to adjust `supportFlairs`, `completenessThreshold`, `fixedFlairName`, and `fixedFollowUpText`.
3. **Seed Knowledge**: Open the subreddit `...` menu and run **GrantDB Support: Moderator Hub > Seed / Sync Knowledge Database** (auto-seeds on first post if empty).

---

## Support

> **Community Support & Feature Requests**
> For questions, troubleshooting, or bug reports, join the official community:
> **[https://www.reddit.com/r/grantdb](https://www.reddit.com/r/grantdb)**

- **User Guide**: [https://www.reddit.com/r/grantdb/wiki/reference-reply-bot/](https://www.reddit.com/r/grantdb/wiki/reference-reply-bot/)
- **Technical Reference**: [https://www.reddit.com/r/grantdb/wiki/index/all-apps/reference-reply-bot/](https://www.reddit.com/r/grantdb/wiki/index/all-apps/reference-reply-bot/)

---

## Legal

- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/reference-reply-bot/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/reference-reply-bot/PRIVACY.md)

---
*Built for Reddit's moderator community.*
