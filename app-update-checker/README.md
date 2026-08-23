> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/app-update-checker)

# App Update Checker

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Hardened-red?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Infrastructure-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Monitoring-8A2BE2?style=for-the-badge)

> **Track installed app versions, discover releases, and receive automated modmail update alerts.**

App Update Checker ensures your subreddit's Devvit tools remain secure and up-to-date. Automatically discovering installed apps and checking them against a continuously-updated snapshot of the Reddit App Directory, it delivers clean, consolidated upgrade summaries straight to your modmail.

---

## At a Glance

- **Automated version audits**: Discover installed apps and check for new releases automatically.
- **Modmail upgrade alerts**: Receive formatted summary tables in modmail highlighting pending updates.
- **Authoritative version data**: Cross-reference against a directly-scraped snapshot of the Reddit App Directory, with npm/GitHub fallbacks for unlisted apps.
- **On-demand menu checks**: Trigger an instant update scan anytime from the subreddit overflow menu.
- **Redis-cached lookups**: The version snapshot is cached per-check to avoid redundant network calls.

---

## The Old Way vs. The App Update Checker Way

| Traditional Workflow | With App Update Checker |
| :--- | :--- |
| Checking the Reddit App Directory manually for updates | **Automated scheduled daily audits** checking every installed app |
| Missing critical bug fixes or security patches in mod tools | **Consolidated modmail notices** sent directly to your team inbox |
| Wondering which version of a custom bot is currently running | **Clear version comparison table** comparing installed vs. latest versions |
| Manually tracking third-party tools and bot usernames | **Automatic app discovery** detecting active moderator bots |
| Dealing with broken bots due to outdated platform APIs | **Proactive release alerts** letting you upgrade on your own schedule |

---

## Built for Seamless App Maintenance

- **Automated App Discovery**: Identifies installed Devvit applications by matching moderator accounts exactly against the Reddit App Directory, with a heuristic fallback for unlisted apps.
- **Authoritative Release Resolution**: Compares against a directly-scraped Reddit App Directory snapshot first, with npm/GitHub fallbacks for apps outside the public directory.
- **Daily Automated Checks**: Runs a scheduled daily background audit (12:00 UTC) with zero impact on subreddit operations.
- **Instant Menu Scans**: Trigger an immediate update check at any moment using **Check for App Updates** in Subreddit Mod Tools.
- **Cache Management Controls**: Clear tracked app data and force a fresh version snapshot with **Reset App Cache**.
- **Native Settings Control**: Specify custom app slugs to monitor and configure update check schedules in App Settings.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/app-update-checker-flowchart.png)

### Your Four-Step Workflow

1. **Discover**: App Update Checker discovers installed Devvit applications from subreddit bot signatures and configured slugs.
2. **Resolve**: Latest published versions are checked against a directly-scraped Reddit App Directory snapshot, falling back to npm/GitHub for unlisted apps.
3. **Compare**: Installed version numbers are compared against upstream release tags to identify pending upgrades.
4. **Notify**: A formatted summary report detailing app upgrade statuses is delivered directly to team modmail.

---

## Quick Setup

1. **Install**: Add **App Update Checker** to your subreddit through the Reddit App Directory.
2. **Configure Settings**: Open **Mod Tools > App Settings > App Update Checker** to adjust notification preferences.
3. **Run Initial Check**: Select **Check for App Updates** from the subreddit overflow menu to generate your first report.
4. **Relax**: Scheduled daily audits will keep your team informed of any future releases.

*No manual app directory checking. Automated update notifications delivered directly to modmail.*

---

## Advanced Capabilities

App Update Checker is engineered for resilient version resolution and lightweight background execution.

- **Authoritative Directory Snapshot**: Reads a directly-scraped Reddit App Directory feed from `raw.githubusercontent.com`, falling back to `registry.npmjs.org` and GitHub release manifests for unlisted apps.
- **Redis-Cached Snapshot**: The directory snapshot is cached for an hour per check run to avoid redundant network calls.
- **Scheduled Cron Runner**: Executes automated checks on a daily cron schedule.
- **Modmail Markdown Formatter**: Formats clean, high-contrast markdown tables with direct links to release notes.

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
