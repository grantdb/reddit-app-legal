> [Full User Guide](https://www.reddit.com/r/grantdb/wiki/postlimiter/) | **Technical Reference & Settings Spec**

# PostLimiter

Category: Moderation  
Version: v0.0.2  
Visibility: Unlisted  
Summary: Configurable independent per-user, per-subject rolling post quota engine for Reddit moderators.

## Overview
Configurable independent per-user, per-subject rolling post quota engine for Reddit moderators.

## Key Features
- Not documented yet.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- PostLimiter: Test Rule Match: Preview which subject and quota rule would apply for a sample title and flair. (Location: subreddit)
- Check PostLimiter Quotas: Inspect quotas, exclude/restore posts, reset limits, manage exemptions, and view logs. (Location: subreddit)

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.tsx)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- enabled: Enable PostLimiter (boolean, default: true). Master toggle for quota checks on new posts.
- quotaMode: Quota Mode (select, default: auto_topic). Auto-Detect Topic works for any topic automatically (same topic = limited, different topic = allowed). Per-Flair gives each post flair its own limit automatically. Custom Subject Rules uses the advanced rules below.
- topicScope: Who Does the Topic Limit Apply To? (Auto-Detect Mode) (select, default: same_user). Same User Only tracks each user independently. All Users limits the same topic across the entire subreddit.
- defaultMaxPosts: Max Posts Per Topic / Subject (number, default: 1). Maximum posts allowed about the same topic within the rolling window (e.g. 1).
- defaultWindowValue: Rolling Time Window (number, default: 24). Rolling cooldown duration (e.g. 24 hours or 7 days).
- defaultTimeUnit: Time Unit (select, default: hours). Time Unit
- defaultAction: Action When Limit Exceeded (select, default: remove_comment). Action When Limit Exceeded
- topicSensitivity: Topic Matching Sensitivity (Auto-Detect Mode) (select, default: balanced). Balanced (default) catches same-topic reposts while allowing different topics (e.g. fishing boat vs sports car).
- overallMaxPosts: Max Overall Posts Per User (0 = Unlimited) (number, default: 0). Hard cap on total posts per user across ALL topics/subjects within the overall window (e.g. 3 posts per 24 hours). Set to 0 to disable.
- overallWindowValue: Overall Limit Rolling Window (number, default: 24). Rolling window for Max Overall Posts Per User (e.g. 24 hours or 7 days).
- overallTimeUnit: Overall Limit Time Unit (select, default: hours). Overall Limit Time Unit
- overallAction: Action When Overall Limit Exceeded (select, default: remove_comment). Action When Overall Limit Exceeded
- overallLimitReason: Too Many Overall Posts - Removal / Report Reason (string, default: DEFAULT_REMOVAL_MESSAGES.overallLimitReason). Placeholders: {maxPosts}, {window}, {remainingTime}, {author}, {subreddit}.
- overallLimitMessage: Too Many Overall Posts - User Message (paragraph, default: DEFAULT_REMOVAL_MESSAGES.overallLimitMessage). Shown when a user hits Max Overall Posts Per User across any topics.
- duplicateTitleReason: Duplicate / Similar Title - Removal / Report Reason (string, default: DEFAULT_REMOVAL_MESSAGES.duplicateTitleReason). Placeholders: {matchedTitle}, {maxPosts}, {window}, {remainingTime}, {author}, {subreddit}.
- duplicateTitleMessage: Duplicate / Similar Title - User Message (paragraph, default: DEFAULT_REMOVAL_MESSAGES.duplicateTitleMessage). Shown when a post is removed for having an identical or very similar title.
- sameTopicReason: Same Topic / Same Link - Removal / Report Reason (string, default: DEFAULT_REMOVAL_MESSAGES.sameTopicReason). Placeholders: {matchedTitle}, {maxPosts}, {window}, {remainingTime}, {author}, {subreddit}.
- sameTopicMessage: Same Topic / Same Link - User Message (paragraph, default: DEFAULT_REMOVAL_MESSAGES.sameTopicMessage). Shown when a post matches an active topic by shared keywords or same external link URL.
- defaultRemovalReason: Subject / Flair Quota - Removal / Report Reason (string, default: DEFAULT_REMOVAL_REASON). Used in Per-Flair and Custom Subject modes. Placeholders: {subject}, {maxPosts}, {window}, {remainingTime}, {author}, {subreddit}, {rulesUrl}.
- defaultUserMessage: Subject / Flair Quota - User Message (paragraph, default: DEFAULT_USER_MESSAGE). Used in Per-Flair and Custom Subject modes. Supports {subject}, {maxPosts}, {window}, {remainingTime}, {author}, {subreddit}, {rulesUrl}.
- subredditRulesUrl: Subreddit Rules / Wiki Link (Optional) (string, default: ). Optional URL automatically linked in user-facing quota messages.
- commentBehavior: Distinguished Mod Comment Behavior (select, default: always). Controls when PostLimiter posts a distinguished moderator comment.
- exemptModerators: Exempt Subreddit Moderators (boolean, default: true). Exempt Subreddit Moderators
- exemptAutoModerator: Exempt AutoModerator (boolean, default: true). Exempt AutoModerator
- exemptUsers: Exempt Usernames (paragraph, default: ). Comma- or newline-separated usernames (with or without u/ prefix).
- exemptUserFlairs: Exempt User Flairs (string, default: ). Comma-separated user flair texts exempt from quotas (case-insensitive).
- exemptPostFlairs: Exempt Post Flairs (string, default: ). Comma-separated post flair texts exempt from quotas (case-insensitive).
- defaultCountRemovedPosts: Count Posts Removed by PostLimiter (boolean, default: false). Recommended OFF: posts removed by PostLimiter do not extend wait time.
- countRemovedByPostLimiter: Keep PostLimiter-Removed Posts Counted (boolean, default: false). Default OFF.
- countRemovedByModerator: Count Posts Removed by Moderators (boolean, default: false). Default OFF: enable if moderator-removed posts should keep counting.
- countRemovedByAutoModerator: Count Posts Removed by AutoModerator (boolean, default: false). Default OFF.
- countDeletedByAuthor: Count Posts Deleted by Author (boolean, default: false). Default OFF: deleting a post frees the user quota slot.
- countMarkedAsSpam: Count Posts Marked as Spam (boolean, default: false). Default OFF.
- recountOnModApproval: Restore Counted Status When Approved by Moderator (boolean, default: true). Restore Counted Status When Approved by Moderator
- reevaluateOnFlairChange: Re-Attribute Subject on Post Flair Change (boolean, default: true). Re-Attribute Subject on Post Flair Change
- primarySubjectName: Primary Subject Name (Optional) (string, default: ). Optional named subject (e.g. "Game A"). Leave blank for Auto-Detect Topic mode.
- primarySubjectSlug: Primary Subject Slug (string, default: ). Primary Subject Slug
- primarySubjectFlairTexts: Matching Post Flair Text(s) (string, default: ). Matching Post Flair Text(s)
- primarySubjectFlairCss: Matching Post Flair CSS Class(es) (string, default: ). Matching Post Flair CSS Class(es)
- primarySubjectTitlePrefixes: Matching Title Prefix(es) (string, default: ). Matching Title Prefix(es)
- primarySubjectTitleTags: Matching Title Tag(s) Anywhere in Title (string, default: ). Matching Title Tag(s) Anywhere in Title
- primarySubjectMaxPosts: Primary Subject Max Posts (number, default: 1). Primary Subject Max Posts
- primarySubjectWindowValue: Primary Subject Rolling Window (number, default: 24). Primary Subject Rolling Window
- primarySubjectTimeUnit: Primary Subject Time Unit (select, default: hours). Primary Subject Time Unit
- primarySubjectAction: Primary Subject Action (select, default: remove_comment). Primary Subject Action
- primarySubjectRemovalReason: Primary Subject Custom Removal Reason (string, default: ). Primary Subject Custom Removal Reason
- primarySubjectMessage: Primary Subject Custom Message (paragraph, default: ). Primary Subject Custom Message
- primarySubjectCountRemoved: Count Removed Posts for Primary Subject (boolean, default: false). Count Removed Posts for Primary Subject
- additionalSubjectsJson: Additional Subject Rules JSON Array (paragraph, default: []). Optional compact JSON array (max MAX_SUBJECT_RULES rules, max MAX_SUBJECTS_JSON_BYTES bytes).
- conflictResolution: Multi-Subject Conflict Resolution (select, default: strictest). Multi-Subject Conflict Resolution
- primaryConflictSubjectSlug: Designated Primary Subject Slug (string, default: ). Designated Primary Subject Slug
- enableRegexMatching: Enable Optional Regex Title Matching (Off by Default) (boolean, default: false). Enable Optional Regex Title Matching (Off by Default)
- fallbackBehavior: Unmatched Post Behavior (Custom Subject / Per-Flair Modes) (select, default: allow). Unmatched Post Behavior (Custom Subject / Per-Flair Modes)
- fallbackRemovalReason: Fallback Removal / Report Reason (string, default: DEFAULT_FALLBACK_REMOVAL_REASON). Fallback Removal / Report Reason
- fallbackMessage: Fallback User Message (paragraph, default: DEFAULT_FALLBACK_MESSAGE). Fallback User Message
- duplicateTitleDetectionEnabled: Enable Duplicate-Title Enforcement (Custom Mode - Off by Default) (boolean, default: false). Only applies in Custom Subject / Per-Flair modes. Auto-Detect Topic mode handles same-topic detection automatically.
- duplicateTitleScope: Duplicate-Title Scope (select, default: same_user). Duplicate-Title Scope
- duplicateTitleSimilarityThreshold: Title Similarity Threshold (0.50 to 1.00) (number, default: 0.85). Title Similarity Threshold (0.50 to 1.00)
- duplicateTitleWindowValue: Duplicate-Title Lookback Window (number, default: 24). Duplicate-Title Lookback Window
- duplicateTitleTimeUnit: Duplicate-Title Time Unit (select, default: hours). Duplicate-Title Time Unit
- duplicateTitleAction: Duplicate-Title Action (select, default: allow). Duplicate-Title Action
- logLevel: Logging Level (select, default: info). Logging Level
- legal_docs: Terms & Privacy (string, default: See help text for official documentation links.). LEGAL_DOCS_URL

## Automation Capabilities
- Submits Automated Comments: Yes — Posts automated comments on target submissions.
- Attaches Removal Notes: No — Does not attach removal notes.
- Approves Content: No — Does not approve content.
- Removes or Filters Content: Yes — Removes or filters non-compliant submissions.
- Dispatches Modmail Alerts: Yes — Sends modmail notifications.
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Sorted Sets (time-series audit logs)

## Setup and Usage
- Install PostLimiter on your subreddit and open Mod Tools -> Installed Apps -> PostLimiter.
- Choose Your Mode in Quick Setup (works immediately with zero subject lists):
- Auto-Detect Topic (Recommended — Default)**: Automatically limits repeat posts about the same topic (e.g. posting *"hey I like this app"* twice is blocked, while posting *"this is a great fishing boat"* and then *"I like this sports car"* is allowed). Choose Same User Only (default) or All Users (subreddit-wide).
- Per-Flair Auto-Quota: Automatically gives every Reddit post flair its own independent limit without configuring flair names.
- Custom Subject Rules (Advanced)**: Define distinct per-category limits in Advanced: Custom Subject Rules (JSON or quick fields) if you want different limits for specific games, apps, or categories.
- Set Max Posts, Rolling Window, and Action (e.g. `1` post per `24 Hours`, `Remove + Comment`) and save.
- ```json
- [
- {
- "name": "Game A",
- "slug": "game-a",
- "priority": 1,
- "flairs": ["Game A"],
- "css": ["game-a"],
- "prefixes": ["[Game A]"],
- "tags": ["[Game A]"],
- "max": 1,
- "window": 24,
- "unit": "hours",
- "action": "remove_comment"
- },
- {
- "name": "Game B",
- "slug": "game-b",
- "priority": 2,
- "flairs": ["Game B"],
- "prefixes": ["[Game B]"],
- "max": 3,
- "window": 7,
- "unit": "days",
- "action": "remove_comment"
- },
- {
- "name": "App X",
- "slug": "app-x",
- "priority": 3,
- "flairs": ["App X"],
- "prefixes": ["[App X]"],
- "max": 2,
- "window": 7,
- "unit": "days",
- "action": "report"
- }
- ]
- ```
- When a single post matches more than one subject (for example, flair `Game B` and title tag `[Support]`):
- Strictest Rule Wins (Default)**: Selects the subject with the lowest effective posting rate (`maxPosts / windowMs`), breaking ties by lowest `maxPosts`, longest window, then alphabetical slug.
- First Matching Rule Wins: Selects the highest-priority subject (lowest `priority` number, or earliest in configuration order).
- Apply All Matching Rules: Checks every matched subject's quota; if any matched subject is exceeded, enforces on the strictest violated rule, otherwise counts the post in all matched subjects.
- Designated Primary Subject Wins: Applies `primaryConflictSubjectSlug` if it is among the matched subjects; otherwise falls back to strictest.
- Duplicate-title enforcement is off by default and must be deliberately enabled by moderators.
- Even when enabled, the default scope is Same User Only, so two different users posting similar titles (e.g. `"My App Update"`) are not blocked unless a moderator explicitly switches the scope to `same_subject` or `entire_subreddit`.
- Open Check PostLimiter Quotas from the subreddit moderator menu (moderator permissions are verified both by Reddit's menu gate and at runtime before execution):
- View User Quotas & History: Enter a username to inspect active counts, rolling windows, expiration timers, matched rules, expired/excluded posts, and recent audit entries.
- Manually Exclude / Restore a Post: Enter a Post ID (`t3_...`), optional reason, and check Confirm Destructive / State-Changing Action to remove or re-include a post in active quota counts.
- Reset User Quota (Single Subject or All Subjects)**: Enter a username (and subject slug for single-subject reset), reason, and check confirmation to clear active quota slots.
- Temporary & Permanent Exemptions: Grant a timed per-subject exemption (in hours) or add/remove a permanent subreddit-wide exemption with confirmation.
- Decision Logs, Metrics & Config Summary: Inspect recent post decisions, operational counters, moderator audit trail, validation errors/warnings, and copyable compact JSON.
- PostLimiter: Test Rule Match: Dry-run any sample title and flair to verify which subject, matching method, and quota rule would apply without modifying any stored data.
- Every state-changing moderator action writes an audit entry recording the moderator username, action, target user, subject, timestamp, and reason.
- Subject not matching expected posts: Run PostLimiter: Test Rule Match from the subreddit menu to inspect which method matched and check for configuration validation errors.
- User still blocked after deleting a post: Verify Count Posts Deleted by Author is turned OFF (default) under Post Lifecycle Counting Policies, or use Check PostLimiter Quotas -> Manually Exclude a Post / Reset User Quota.
- Regex rule not firing: Confirm Enable Optional Regex Title Matching is enabled and check View Configuration Summary for unsafe-pattern validation errors (nested quantifiers and backreferences are rejected for safety).
- Settings size limit: `additionalSubjectsJson` supports up to 16,384 bytes and 50 subject rules; use compact keys (`flairs`, `css`, `prefixes`, `tags`, `max`, `window`, `unit`, `action`) for large rule sets.
- All data is stored exclusively inside Reddit's subreddit-scoped Devvit Redis storage; no external databases or third-party services are used.
- Active quota records expire automatically after the configured rolling window plus a 24-hour grace period, and a bounded 6-hour scheduled cleanup job prunes expired sets without scanning the Redis keyspace.
- Decision logs, post history indexes, duplicate-title entries, and moderator audit logs are retained for at most 30 days. Temporary exemptions expire automatically at their configured duration.

## Troubleshooting
- Subject not matching expected posts: Run PostLimiter: Test Rule Match from the subreddit menu to inspect which method matched and check for configuration validation errors.
- User still blocked after deleting a post: Verify Count Posts Deleted by Author is turned OFF (default) under Post Lifecycle Counting Policies, or use Check PostLimiter Quotas -> Manually Exclude a Post / Reset User Quota.
- Regex rule not firing: Confirm Enable Optional Regex Title Matching is enabled and check View Configuration Summary for unsafe-pattern validation errors (nested quantifiers and backreferences are rejected for safety).
- Settings size limit: `additionalSubjectsJson` supports up to 16,384 bytes and 50 subject rules; use compact keys (`flairs`, `css`, `prefixes`, `tags`, `max`, `window`, `unit`, `action`) for large rule sets.

## Version History
0.0.2 — 2026-11-24
- Phase 1 + Phase 2: Independent per-subject rolling quotas, lifecycle triggers, conflict resolution, moderator operations hub, audit trail, scheduled cleanup, and disabled-by-default duplicate-title foundation

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/postlimiter/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/postlimiter/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/postlimiter)
- [Support](https://www.reddit.com/r/grantdb)