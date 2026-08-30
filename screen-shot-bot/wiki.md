# Screen-Shot Bot

Category: Rendering  
Version: v1.0.77  
Visibility: Public  
Summary: Automated screen-capture and visual logging utility.

## Overview
Automated screen-capture and visual logging utility.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/screen-shot-bot-flowchart.png)

## Key Features
- Automated AI Transcription: Integrates with Gemini to instantly and accurately extract precise text strings from complex, grainy, or poorly lit technical images.
- Searchable Indexing: By converting static images of crash logs into text-based stickied comments, it ensures that your subreddit's error reports are fully searchable by future users experiencing the same issue.
- Configurable Targets: Granular settings allow you to choose exactly what the bot looks for. You can configure it to transcribe *all* terminal images, or only activate when it detects specific contexts (like Errors, System Info, or Config files).
- Mod Approval Coverage: Safely operates alongside your existing moderation workflow. It will automatically check new posts, and intelligently re-process posts if they are held and later approved by a moderator.
- Manual Actions: Moderators can manually trigger an on-demand transcription of older posts using the Mod Actions menu.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)
- http: External HTTP Fetch access [Domains: generativelanguage.googleapis.com, i.redd.it, preview.redd.it, imgur.com]

## Triggers and Activation
### Menu Actions
- Screenshot Bot: Extract Text: Uses Gemini Vision to extract text from screenshots or terminal photos (Location: post)

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- legal_docs: Terms & Privacy (string, default: See help text for official documentation links.). LEGAL_DOCS_URL
- geminiApiKey: Gemini API Key (string, default: -). Gemini API Key
- characterLimit: Comment Character Limit (number, default: 1500). Maximum characters in a comment before truncating.
- max_comments_per_hour: Hourly Comment Rate Limit (number, default: 30). Maximum bot comments allowed per hour across the subreddit for automated runs. Hard-capped at 60.
- comment_format: Comment Format Style (select, default: spoiler). Select how the stickied comment should be rendered to save vertical space.
- detection_target: Extraction Target (select, default: all). Select what types of terminal screenshots the bot should look for.
- automation_mode: Automation Mode (select, default: auto). Select whether the bot should automatically process new posts or only run when manually triggered.

## Automation Capabilities
- Submits Automated Comments: Yes — Posts automated comments on target submissions.
- Attaches Removal Notes: No — Does not attach removal notes.
- Approves Content: No — Does not approve content.
- Removes or Filters Content: No — Does not remove or filter content.
- Dispatches Modmail Alerts: No — Does not send modmail notifications.
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)

## Setup and Usage
- Install: Add Screen Shot Bot to your subreddit via the App Directory.
- App Settings:
- Add your Google Gemini API key to the settings.
- Select your "Extraction Target" from the dropdown list.
- Usage: The bot runs automatically. To use it manually on an old post, use the "Extract text from image (Gemini)" menu item in the post's mod menu.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
1.0.77 — 2026-08-15
- Standard fleet synchronization and maintenance.

1.0.76 — 2026-08-10
- Standard fleet synchronization and maintenance.

1.0.75 — 2026-08-04
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/screen-shot-bot/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/screen-shot-bot/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/screen-shot-bot)
- [Support](https://www.reddit.com/r/grantdb)