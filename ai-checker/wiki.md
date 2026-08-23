# AI Checker

Category: Security  
Version: v0.0.81  
Visibility: Public  
Summary: Moderator-triggered AI detection engine. Upgraded to native Gemini 1.5 Flash for high-speed analysis.

## Overview
Moderator-triggered AI detection engine. Upgraded to native Gemini 1.5 Flash for high-speed analysis.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/ai-checker-flowchart.png)

## Key Features
- Not documented yet.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)
- http: External HTTP Fetch access [Domains: generativelanguage.googleapis.com, api.gptzero.me, api.sightengine.com, api.thehive.ai, i.redd.it, preview.redd.it, external-preview.redd.it, i.imgur.com]

## Triggers and Activation
### Menu Actions
- Check AI Content: Moderator menu action (Location: post)

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.tsx)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- detectionProvider: Detection Provider (select, default: DetectionProvider.Gemini). Detection Provider
- resultCommentTemplate: Result Comment Template (paragraph, default: This post has been reviewed with the community AI detection tool.

**Verdict:** {verdict}
**Score:** {score}/10
**Provider:** {provider}
**Confidence:** {confidence}
**Content Type:** {content_type}

*This is an automated indicator intended to assist moderator review, not a definitive action. Contact moderators via modmail with any questions.*). Result Comment Template
- includeProviderConfidence: Include Provider Confidence in Comment (boolean, default: true). Include Provider Confidence in Comment
- distinguishResultComment: Distinguish Result Comment as Moderator (boolean, default: true). Distinguish Result Comment as Moderator
- lockResultComment: Lock Result Comment (boolean, default: false). Lock Result Comment
- sendModmailCopy: Send Modmail Copy to Moderators (boolean, default: false). Send Modmail Copy to Moderators
- autoScanPosts: Enable Auto-Scan on New Posts (boolean, default: false). Enable Auto-Scan on New Posts
- delayedProcessingSeconds: Processing Delay (seconds) (number, default: 20). Delay before scanning to verify post eligibility (min 5s, max 100s).
- minConfidenceThreshold: Minimum Confidence Threshold (0.0 - 1.0) (number, default: 0.5). Ignore detections below this confidence level.
- gemini_api_key: Gemini API Key (string, default: -). Required if using Gemini provider. Get a key at aistudio.google.com
- gptzero_api_key: GPTZero API Key (string, default: -). Required if using GPTZero provider.
- sightengine_api_user: Sightengine API User (string, default: -). Required if using Sightengine provider.
- sightengine_api_secret: Sightengine API Secret (string, default: -). Required if using Sightengine provider.
- hive_api_key: Hive API Key (string, default: -). Required if using Hive provider.
- hive_project_id: Hive Project ID (string, default: text_ai_generated). Hive Project ID

## Automation Capabilities
- Submits Automated Comments: Yes — Posts automated comments on target submissions.
- Attaches Removal Notes: No — Does not attach removal notes.
- Approves Content: No — Does not approve content.
- Removes or Filters Content: No — Does not remove or filter content.
- Dispatches Modmail Alerts: Yes — Sends modmail notifications.
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)

## Setup and Usage
- Install: Add AI Checker to your subreddit through the Reddit App Directory.
- Configure Provider: Open Mod Tools > App Settings > AI Checker and add your provider API key.
- Set Preferences: Choose between on-demand menu auditing or automated background scanning.
- Save: Start evaluating synthetic content directly from your native moderation workflow.
- No external browser extensions required. Multi-model AI detection right inside Reddit.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.81 — 2026-08-15
- Standard fleet synchronization and maintenance.

0.0.80 — 2026-08-02
- Standard fleet synchronization and maintenance.

0.0.79 — 2026-08-02
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/ai-checker/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/ai-checker/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/ai-checker)
- [Support](https://www.reddit.com/r/grantdb)