> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/app-update-checker)

# App Update Checker

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Hardened-red?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Infrastructure-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Monitoring-8A2BE2?style=for-the-badge)

> **Track installed app versions, discover new releases, and receive automated modmail update alerts for any subreddit.**

App Update Checker ensures your subreddit's Devvit tools and moderation bots remain secure and up-to-date. By automatically discovering installed applications, establishing baseline versions on install, and running silent daily checks against the Reddit App Directory, it keeps your mod team informed whenever an update is published.

---

## At a Glance

- **Automated zero-config setup**: Discovers installed apps and establishes your starting baseline automatically upon installation.
- **Silent daily audits**: Runs a lightweight background check every day at 12:00 UTC with zero modmail spam—alerts are sent only when a new update is released.
- **Modmail upgrade alerts**: Delivers high-contrast summary tables with direct links to update pages on the Reddit App Directory.
- **Universal directory support**: Cross-references against 150+ public apps in the Reddit App Directory and official developer manifests.
- **On-demand moderator tools**: Trigger an instant update scan or sync baselines anytime from the subreddit overflow menu (`...`).

---

## The Old Way vs. The App Update Checker Way

| Traditional Workflow | With App Update Checker |
| :--- | :--- |
| Checking the Reddit App Directory manually for updates | **Automated scheduled daily audits** checking every installed app |
| Missing critical bug fixes or security patches in mod tools | **Consolidated modmail release alerts** sent directly to your team inbox |
| Wondering which version of an app is currently running | **Clear version comparison table** comparing installed vs. latest versions |
| Manually tracking third-party tools and bot usernames | **Automatic app discovery** detecting active moderator bots |
| Dealing with broken bots due to outdated platform APIs | **Proactive release alerts** letting you upgrade on your own schedule |

---

## Built for Seamless Community Maintenance

- **Automated App Discovery**: Identifies installed Devvit applications by matching moderator accounts against known app manifests.
- **Auto-Baseline on Install**: Locks in current versions upon installation so you only receive alerts for future releases.
- **Silent Daily Audits**: Runs daily background checks without filling your modmail when everything is current.
- **Instant Menu Scans**: Trigger an immediate update check at any moment using **Check for App Updates** in Subreddit Mod Tools.
- **Sync Installed Baselines**: Select **Sync Installed Baselines** after updating apps in Mod Tools to lock in new versions.
- **Cache Management Controls**: Clear tracked app data and force a fresh discovery scan with **Reset App Cache**.
- **Native Settings Control**: Specify custom app slugs to monitor, toggle unlisted bot reporting, and configure check schedules in App Settings.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/app-update-checker-flowchart.png)

### Your Four-Step Lifecycle

1. **Discover**: App Update Checker discovers installed Devvit applications from subreddit bot signatures and configured custom slugs.
2. **Auto-Baseline**: Sets detected app versions as the active baseline and delivers a one-time Welcome Report to Modmail.
3. **Silent Audit**: Runs automated daily checks against authoritative Reddit App Directory snapshots.
4. **Notify**: Delivers an actionable Modmail alert only when an app author publishes a new release.

---

## Quick Setup

1. **Install**: Add **App Update Checker** to your subreddit through the Reddit App Directory.
2. **Review Welcome Report**: Check your Modmail for the initial monitored inventory and baseline summary.
3. **Configure Settings (Optional)**: Open **Mod Tools > App Settings > App Update Checker** to adjust notification preferences or add custom slugs.
4. **Relax**: Scheduled daily audits will keep your team informed of any future releases.

*No manual app directory checking. Automated update notifications delivered directly to modmail.*

---

## Advanced Capabilities

App Update Checker is engineered for resilient version resolution and lightweight background execution.

- **Authoritative Directory Snapshot**: Reads a continuously updated Reddit App Directory feed and manifest from `raw.githubusercontent.com`.
- **Redis-Cached Snapshot**: The directory snapshot is cached for an hour per check run to avoid redundant network calls.
- **Scheduled Cron Runner**: Executes automated checks on a daily cron schedule at 12:00 UTC.
- **Modmail Markdown Formatter**: Formats clean, high-contrast markdown tables with direct links to app install pages.

---

## Designed to Assist Moderators

App Update Checker provides automated version monitoring and status reporting to assist in maintaining installed community tools. Update summaries serve as informational alerts—human moderators retain full authority over which apps are installed, updated, or removed.

---

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include:
- The app name.
- What you expected to happen.
- What happened instead.
- Any error message.
- Screenshots or relevant details.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/app-update-checker/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/app-update-checker/PRIVACY.md)

---
*Built for Reddit's moderator community.*
