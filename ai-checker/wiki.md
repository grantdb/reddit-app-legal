# AI Checker

Category: Security  
Version: v0.0.91  
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
- AI Checker: Scan Post: Manually scan this post for AI-generated content (Location: post)

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.tsx)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- detectionProvider: Detection Mode / Provider (select, default: DetectionProvider.Consensus). IMPORTANT: Using a single AI provider can lead to false positives or false negatives, especially on stylized art or edge cases. For best accuracy, configure 2 or more API keys below and use Multi-AI Consensus mode so engines cross-validate each other.
- resultCommentTemplate: Result Comment Template (paragraph, default: This post has been reviewed with the community AI detection tool.

**Verdict:** {verdict}
**Score:** {score}/10
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
- gemini_api_key: Gemini API Key (Text & Image) (string, default: -). Native multimodal engine. Get a free API key at aistudio.google.com. Combining this with Sightengine or Hive provides optimal accuracy.
- sightengine_api_user: Sightengine API User (Image) (string, default: -). Dedicated visual forensics engine for image and art detection. Recommended alongside Gemini.
- sightengine_api_secret: Sightengine API Secret (Image) (string, default: -). Secret key from sightengine.com dashboard.
- gptzero_api_key: GPTZero API Key (Text) (string, default: -). Dedicated text perplexity and burstiness detection engine for written submissions.
- hive_api_key: Hive Moderation API Key (Text & Image) (string, default: -). Enterprise AI generation detection engine from thehive.ai.
- hive_project_id: Hive Project ID (string, default: text_ai_generated). Hive Project ID

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
0.0.91 — 2026-11-11
- Devvit SDK v0.15.2 baseline and minor/patch dependency maintenance update.

0.0.90 — 2026-11-04
- Standard fleet synchronization and maintenance.

0.0.90 — 2026-11-03
- Upgraded Gemini model provider from deprecated gemini-2.5-flash / gemini-2.5-pro to gemini-3.5-flash-lite for both text and multimodal image analysis, resolving free-tier 429 quota exhaustion.
- Aligned devvit.json manifest trigger declaration with Blocks runtime container standards by migrating trigger to blocks.triggers, resolving repeated /internal/on-post-create fetch failure errors.
- Enhanced Gemini API error handling to extract clear, concise error messages from API responses.
- Added comprehensive Vitest unit test suite covering GeminiAdapter text and image payload structures, 1-10 scoring normalization, and error handling.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/ai-checker/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/ai-checker/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/ai-checker)
- [Support](https://www.reddit.com/r/grantdb)