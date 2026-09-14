> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/sub-setup)

# Sub Setup

## Purpose
Interactive subreddit setup guide and configuration wizard for Reddit communities.

`sub-setup` guides moderators through an in-depth, 19-section setup across 9 progressive wizard steps. It combines automated API inspections with persistent manual checklists, direct 1-click Mod Tools launchers, official Reddit documentation references, prioritized quick wins, and on-demand Modmail export.

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/sub-setup-flowchart.png)

### Your Four-Step Workflow

1. **Moderator Launch**: A moderator clicks **Run Subreddit Setup Audit** in the subreddit menu. The server retrieves or generates a private, stealth custom post accessible only to moderators.
2. **Dual Audit & Interactive Wizard**: The app loads an interactive 9-step React webview. Automated checks inspect 8 API-accessible areas, while guided checklists track manual settings with Redis persistence.
3. **Step-by-Step Configuration**: Moderators work through settings, check off manual tasks with optimistic UI updates, launch 1-click Mod Tools deep links, or batch-complete steps.
4. **Export & Sharing**: On demand, moderators can dispatch a structured Markdown summary directly to Modmail (Mod Discussions) or copy progress snippets to clipboard for team coordination.

## Major Features

- **Interactive 9-Step Wizard**: Structured progression from community identity and AutoModerator to rules, flairs, safety filters, onboarding, team health, and operations.
- **Mod-Only Stealth Post**: Runs in an expanded custom post that is automatically removed from the public subreddit feed so it never clutters member views.
- **Persistent Manual Checklists**: Tracks your manual verification progress in Redis (`v1` namespace), completely decoupled from API audit runs so you never lose progress.
- **Optimistic UI Updates**: Checkboxes update instantaneously with automatic rollback and toast notifications on network interruption.
- **Batch Step Completion**: "Mark All Complete in This Step" allows rapid completion of verified configuration areas.
- **Remaining Items Quick Filter**: 1-click modal listing all pending tasks across the entire subreddit with direct jump navigation.
- **Rate-Limited Audit Engine**: 60-second cooldown protects platform resources and displays live retry timers.
- **Direct Mod Tools Launchers**: Every section includes deep links with confirmed or best-effort routing to the exact Mod Tools page.
- **Official Documentation**: 30+ official Reddit Help Center and AutoModerator documentation links categorized by relevance.
- **Zero-PII & Privacy-First**: Reads only high-level community settings; never inspects private user profiles, post bodies, or modmail conversations.
- **On-Demand Modmail Delivery**: Safe multi-part chunking (under 9,000 characters per message) delivers formatted reports to team Mod Discussions on demand.

## Install / Use

1. Install **Sub Setup** on your subreddit.
2. Open your subreddit's menu and select **Run Subreddit Setup Audit**.
3. You will be routed directly to the interactive setup guide.
4. Complete the 9 steps at your own pace — your progress is saved automatically.
5. When ready, click **Send to Modmail** in Step 9 to archive your setup report in Mod Discussions.

## 9 Wizard Steps (19 Configuration Sections)

1. **Step 1 — Community Identity & Settings**: Title, description, sidebar length, community avatar, banner image, discoverability, and NSFW status.
2. **Step 2 — AutoModerator Protection**: Wiki configuration existence, rule blocks, YAML syntax validation (tab detection), new account filtering, and action reasons.
3. **Step 3 — Rules Hub & Enforcement**: Rule definitions, depth, rule fatigue checks, removal reasons, and pre-submission Post Check triggers.
4. **Step 4 — Flairs & Taxonomy**: Post flair enablement, template counts, user flair enablement, media uploads, and wiki pages.
5. **Step 5 — Safety Filters & Auto-Triage**: Native Crowd Control, Reputation Filter, Ban Evasion Filter, and Poster Eligibility.
6. **Step 6 — Onboarding & Community Guide**: New member welcome messages, resource links, flair prompts, saved responses, and temporary event overrides.
7. **Step 7 — Moderator Team & Notifications**: Team coverage, single-point-of-failure redundancy analysis, scoped permissions, and activity alert thresholds.
8. **Step 8 — Operations & Insights**: Queue daily triage routines, Mod Log audit trails, Modmail workflow, and Mod Insights traffic growth.
9. **Step 9 — Final Review & Export**: Overall score summary, remaining quick wins, progress reset, clipboard copy, and Modmail export.

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/sub-setup/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/sub-setup/PRIVACY.md)

---
*Built for Reddit's moderator community.*
