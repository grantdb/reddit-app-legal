# Privacy Policy for GimmeCode Guard

Last updated: September 24, 2026

## Overview

GimmeCode Guard is an automated moderation application built on the Reddit Developer Platform (Devvit). The application helps subreddit moderation teams detect, score, and manage low-effort code requests and code-begging comments to preserve technical discussion quality.

## Information Stored and Processed

To deliver its graduated moderation features (warning replies, mod queue reports, and comment removals), GimmeCode Guard processes and stores the following operational data within Reddit's internal, encrypted Redis database:

1. **Account-Linked Cumulative Scores**:
   - When a comment matches known low-effort code request patterns, a numerical score is calculated based on phrase weighting and code-block evaluation.
   - Cumulative infraction scores and strike counts are stored in Redis keyed by the user's internal Reddit account identifier (`authorId`).
   - This account-linked record enables graduated enforcement (e.g. polite warning on first infraction, mod queue review on repeated violations).

2. **Flagged Comment Text and Audit Records**:
   - For comments that meet or exceed detection thresholds (score ≥ 3), the app temporarily logs a structured audit record containing the comment ID, author username, author ID, timestamp, violation reasons, and the snippet of flagged comment text.
   - These records are stored in an internal Redis sorted set scoped exclusively to the subreddit where the comment was posted.
   - This log is accessible only to authorized subreddit moderators via the native Mod Tools menu and on-demand Modmail summary reports.

## Data Retention Periods

GimmeCode Guard enforces strict, automated data retention limits:

- **Cumulative Scores and Strikes (90-Day Rolling TTL)**: User scores and strike tallies automatically expire and are permanently deleted from Redis **90 days** after the most recent infraction (`STRIKE_TTL_MS = 90 days`). If a user incurs no new violations within 90 days, their scores reset to 0.
- **Temporary Action Cooldowns (24 Hours)**: Automated polite warning reply cooldowns and high-offense modmail alert cooldowns automatically expire after **24 hours**.
- **Audit Flags Queue (Capped Log)**: The subreddit audit log is capped at a maximum of **500 flag records**. Older entries are automatically pruned when new records are added.

## Data Deletion & Right to Be Forgotten

GimmeCode Guard provides comprehensive, automated and on-demand deletion mechanisms:

1. **Real-Time Comment Deletion**:
   - When a comment is deleted by its author or by subreddit moderators, GimmeCode Guard receives Reddit's real-time `CommentDelete` event.
   - Upon receipt of this event, the app immediately searches the subreddit's flags log and **permanently removes the stored comment text and all associated flag records** for that comment ID.

2. **Account Deletion & Anonymization**:
   - If a Reddit user account is deleted or ceases to exist (`[deleted]`), GimmeCode Guard purges all stored account-linked cumulative scores, strike records, action cooldowns, and all copied comment snippets associated with that author ID across the subreddit database.

3. **On-Demand Moderator Database Wipe**:
   - Subreddit moderators have direct administrative control to purge the entire database at any time. Selecting **Reset User Database** from the GimmeCode Guard moderator menu permanently deletes all cumulative user scores, strikes, and logged comment records for the subreddit.

## Third-Party Data Sharing & External Communications

- **Zero External Transmission**: GimmeCode Guard runs entirely on Reddit's secure developer infrastructure. It does not communicate with external servers, databases, or third-party APIs.
- **Zero Third-Party Sharing**: No user data, comment text, scores, or identifiers are ever sold, shared, or transmitted to any external parties.
- **No Personal Identifiable Information (PII)**: GimmeCode Guard does not collect, request, or store names, email addresses, IP addresses, location data, or private messages.

## Contact & Inquiries

For questions regarding this Privacy Policy, data handling, or to request manual deletion of data, please contact the developer via Reddit Modmail at [r/grantdb](https://www.reddit.com/r/grantdb/).
