# Post Title Check

Category: Validation  
Version: v0.0.84  
Visibility: Public  
Summary: Real-time title validation against community guidelines. Now with support for customizable removal reasons per rule.

## Overview
Real-time title validation against community guidelines. Now with support for customizable removal reasons per rule.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/post-title-check-flowchart.png)

## Key Features
- Not documented yet.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- PostSubmit: Subscribed in main.ts via Devvit.addTrigger({ event: 'PostSubmit' }).
- PostCreate: Subscribed in main.ts via Devvit.addTrigger({ event: 'PostCreate' }).
- AppInstall: Subscribed in main.ts via Devvit.addTrigger({ event: 'AppInstall' }).
- AppUpgrade: Subscribed in main.ts via Devvit.addTrigger({ event: 'AppUpgrade' }).

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- legal_docs: Terms & Privacy (string, default: See help text for official documentation links.). LEGAL_DOCS_URL
- removalMessage: Global Preamble Message (string, default: Hi! Your post was automatically removed because its title does not meet the requirements for r/{subreddit}.). The preamble added to every removal comment. The specific rule violation will be appended automatically.
- removalCommentTemplate: Removal Comment Template (string, default: {preamble}

**Reason:** {reason}). Full template for the removal comment. Use {preamble} for the global preamble and {reason} for the specific rule reason. Markdown is supported.
- minWordCount: Minimum Word Count (number, default: 3). Posts whose titles have fewer words than this will be removed. Set to 0 to disable minimum word count checking.
- reasonMinWordCount: Custom Removal Reason (paragraph, default: Your title is too short (minimum {minWordCount} words required). Please use more words so the post is descriptive enough for other users.). The reason appended to the removal comment when this rule is violated. Use {minWordCount} for required word count.
- bannedPhrases: Banned Phrases (comma-separated) (string, default: ). A comma-separated list of phrases. Any post title containing one of these phrases will be removed. Case-insensitive. Single words are matched as whole words only (e.g. "SYN" will NOT match "SYNWAVE"). Multi-word phrases are matched anywhere in the title.
- reasonBannedPhrases: Custom Removal Reason (paragraph, default: Your title contains a banned phrase: "{phrase}". Please rewrite your title without this phrase.). The reason appended to the removal comment when this rule is violated. Use {phrase} to inject the matched phrase.
- requireBrackets: Require Brackets [...] (boolean, default: false). When enabled, post titles must contain at least one bracketed tag, e.g. [Game] or [Tool].
- reasonRequireBrackets: Custom Removal Reason (paragraph, default: Your title is missing a required [Tag] (e.g. `[Game]`, `[Tool]`). Please include a bracketed category tag.). The reason appended to the removal comment when this rule is violated.
- englishOnly: English / ASCII Only (boolean, default: false). When enabled, post titles must consist of printable ASCII / Latin characters or emojis only. Foreign non-Latin scripts will be removed.
- reasonEnglishOnly: Custom Removal Reason (paragraph, default: Your title contains characters outside of the supported (English) character set. Please rewrite your title using standard English characters.). The reason appended to the removal comment when this rule is violated.
- moderatorExempt: Exempt Moderators from Title Checks (boolean, default: false). When enabled, posts submitted by subreddit moderators will skip all title rule checks.

## Automation Capabilities
- Submits Automated Comments: Yes — Posts automated comments on target submissions.
- Attaches Removal Notes: No — Does not attach removal notes.
- Approves Content: No — Does not approve content.
- Removes or Filters Content: Yes — Removes or filters non-compliant submissions.
- Dispatches Modmail Alerts: No — Does not send modmail notifications.
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)

## Setup and Usage
- Install: Add Post Title Check to your subreddit through the Reddit App Directory.
- Configure Rules: Open Mod Tools > App Settings > Post Title Check to set word counts and required tags.
- Add Banned Words: Enter prohibited clickbait phrases separated by commas.
- Save: Automated title validation begins immediately on all incoming community submissions.
- No complex AutoMod regex scripts required. Clean, professional titles across your entire feed.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.84 — 2026-09-04
- Standard fleet synchronization and maintenance.

0.0.83 — 2026-09-02
- Standard fleet synchronization and maintenance.

0.0.83 — 2026-09-02
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/post-title-check/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/post-title-check/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/post-title-check)
- [Support](https://www.reddit.com/r/grantdb)