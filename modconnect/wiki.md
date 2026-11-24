> [Full User Guide](https://www.reddit.com/r/grantdb/wiki/modconnect/) | **Technical Reference & Settings Spec**

# ModConnect

Category: Moderation  
Version: v0.0.2  
Visibility: Unlisted  
Summary: ModConnect helps community moderators recruit, review, and onboard moderators directly inside Reddit.

## Overview
ModConnect helps community moderators recruit, review, and onboard moderators directly inside Reddit.

## Key Features
- Automatic account eligibility checks (minimum account age, subreddit karma, ban/mod-note flags).
- Graded onboarding quizzes and reusable subreddit-level onboarding templates.
- Configurable multi-moderator approval thresholds and structured interview rubrics.
- Optional exportable audit summaries and recruitment cycle archiving.

## Permissions Used
- reddit: Reddit API access (moderation actions, post/comment fetching, modmail)
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- AppInstall: Delivered by Reddit event router to endpoint /internal/trigger/app-install.
- AppUpgrade: Delivered by Reddit event router to endpoint /internal/trigger/app-upgrade.

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- newApplicationSubject: New Application Modmail Subject (string, default: [ModConnect] New application for {{roleTitle}} from u/{{applicantUsername}}). Placeholders: {{roleTitle}}, {{applicantUsername}}, {{subredditName}}, {{submittedAt}}
- newApplicationBody: New Application Modmail Template (paragraph, default: A new moderator application has been submitted for **{{roleTitle}}** in r/{{subredditName}}.

- **Applicant:** u/{{applicantUsername}}
- **Submitted:** {{submittedAt}}
- **Review Candidate:** [Open ModConnect Dashboard]({{dashboardUrl}})

Open the ModConnect dashboard to review answers, leave a score, and update pipeline status.). Placeholders: {{roleTitle}}, {{applicantUsername}}, {{subredditName}}, {{submittedAt}}, {{dashboardUrl}}
- acceptedSubject: Accepted Candidate Modmail Subject (string, default: Update on your {{roleTitle}} application for r/{{subredditName}}). Placeholders: {{roleTitle}}, {{applicantUsername}}, {{subredditName}}
- acceptedBody: Accepted Candidate Modmail Template (paragraph, default: Hello u/{{applicantUsername}},

Thank you for applying for **{{roleTitle}}** in r/{{subredditName}}. We are pleased to let you know that your application has been accepted!

To get started, please open your onboarding checklist here:
[Open Your Onboarding Checklist]({{postUrl}})

We look forward to welcoming you to the moderation team.). Placeholders: {{roleTitle}}, {{applicantUsername}}, {{subredditName}}, {{postUrl}}
- rejectedSubject: Rejected Candidate Modmail Subject (string, default: Update on your {{roleTitle}} application for r/{{subredditName}}). Placeholders: {{roleTitle}}, {{applicantUsername}}, {{subredditName}}
- rejectedBody: Rejected Candidate Modmail Template (paragraph, default: Hello u/{{applicantUsername}},

Thank you for taking the time to apply for **{{roleTitle}}** in r/{{subredditName}}. After careful consideration, we will not be moving forward with your application at this time.

We appreciate your interest in supporting the community and encourage you to stay involved.). Placeholders: {{roleTitle}}, {{applicantUsername}}, {{subredditName}}

## Automation Capabilities
- Submits Automated Comments: No — Does not submit automated comments.
- Attaches Removal Notes: No — Does not attach removal notes.
- Approves Content: Yes — Approves content.
- Removes or Filters Content: Yes — Removes or filters non-compliant submissions.
- Dispatches Modmail Alerts: Yes — Sends modmail notifications.
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Hashes (structured records & alias indices)
- Sorted Sets (time-series audit logs)
- Key patterns: node:http, node:crypto

## Setup and Usage
- Install: Add app via Reddit App Directory.
- Configure: Open Mod Tools -> App Settings in your subreddit to configure options.
- Launch: Use mod menu or triggers as configured.

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
0.0.2 — 2026-11-24
- Build Phase 1 ModConnect MVP: role creation, interactive application post, moderator review & pipeline, archivable modmail notifications, onboarding checklist, and basic recruiting metrics

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/modconnect/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/modconnect/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/modconnect)
- [Support](https://www.reddit.com/r/grantdb)