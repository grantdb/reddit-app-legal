> **User Guide & Overview** | [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/app-update-checker)

# App Update Checker

> **Track installed app versions, discover new releases, and receive automated modmail update alerts for any subreddit.**

App Update Checker ensures your subreddit's Devvit tools and moderation bots remain secure and up-to-date. Powered by an automated backend directory scraper that continuously tracks public Reddit App Directory releases, it runs silent daily audits and keeps your mod team informed whenever an app author publishes a new version.

---

## At a Glance

- **Automated backend directory scraper**: Continuously monitors and extracts release versions from public Reddit App Directory listings into an up-to-date manifest feed.
- **Clear, verified onboarding**: Guides your mod team to update apps in Mod Tools and sync baseline tracking on initial install.
- **Silent daily audits**: Runs a lightweight background check every day at 12:00 UTC with zero modmail spam—alerts are sent only when a new update is published.
- **Archivable Modmail alerts**: Delivers clean, text-formatted summary tables directly to your Modmail Inbox where they can be archived to keep your inbox clean.
- **Universal directory support**: Cross-references against 150+ public apps in the Reddit App Directory and official developer manifests.
- **Consolidated moderator controls**: Access on-demand scans, baseline syncing, and cache resets from a single **App Update Checker** menu popout.

---

## How It Works: The 4-Step Operational Pipeline

### 01 · Discover
> **Moderator bot & custom slug detection**
> - App Update Checker discovers installed Devvit applications from subreddit moderator bot signatures and configured custom slugs.

---

### 02 · Setup & Sync
> **Baseline version confirmation**
> - Update your apps via Reddit's **Mod Tools > Installed Apps**, then run **Sync All Apps as Updated** in the menu popout to lock in baselines.

---

### 03 · Silent Audit
> **Scheduled daily version comparison**
> - Runs automated daily checks at 12:00 UTC, comparing active community tools against version feeds compiled by our backend directory scraper.

---

### 04 · Notify
> **Archivable Modmail Inbox alerts**
> - Delivers an actionable Modmail alert only when an app author publishes a new release (or immediately on manual scan).

---

## Quick Setup

1. **Install**: Add **App Update Checker** to your subreddit through the Reddit App Directory.
2. **Update Apps in Mod Tools**: Open **Mod Tools > Installed Apps** in Reddit and update any outdated applications.
3. **Sync Baseline**: Open the subreddit menu (`...`), select **App Update Checker**, and choose **Sync All Apps as Updated** to establish your confirmed tracking baseline.

---

## Support

> **Need Help?** Post in [https://www.reddit.com/r/grantdb](https://www.reddit.com/r/grantdb) with the app name, what you expected, what happened, and any error text or screenshots.
>
> - **User Guide**: [https://www.reddit.com/r/grantdb/wiki/app-update-checker/](https://www.reddit.com/r/grantdb/wiki/app-update-checker/)
> - **Technical Reference**: [https://www.reddit.com/r/grantdb/wiki/index/all-apps/app-update-checker/](https://www.reddit.com/r/grantdb/wiki/index/all-apps/app-update-checker/)

---

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/app-update-checker/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/app-update-checker/PRIVACY.md)

---
*Built for Reddit's moderator community.*
