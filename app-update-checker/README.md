> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/app-update-checker)

# App Update Checker

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Hardened-red?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Infrastructure-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Monitoring-8A2BE2?style=for-the-badge)

> **Track installed app versions, discover new releases, and receive automated modmail update alerts for any subreddit.**

App Update Checker ensures your subreddit's Devvit tools and moderation bots remain secure and up-to-date. Powered by an automated backend directory scraper that continuously tracks public Reddit App Directory releases, it runs silent daily audits and keeps your mod team informed whenever an app author publishes a new version.

---

## At a Glance

- **Automated backend directory scraper**: Continuously monitors and extracts release versions from public Reddit App Directory listings into an up-to-date manifest feed.
- **Clear, verified onboarding**: Guides your mod team to update apps in Mod Tools and sync baseline tracking on initial install.
- **Silent daily audits**: Runs a lightweight background check every day at 12:00 UTC with zero modmail spam—alerts are sent only when a new update is published.
- **Modmail upgrade alerts**: Delivers clean, text-formatted summary tables with direct links to update pages on the Reddit App Directory.
- **Universal directory support**: Cross-references against 150+ public apps in the Reddit App Directory and official developer manifests.
- **Consolidated moderator controls**: Access on-demand scans, baseline syncing, and cache resets from a single **App Update Checker** menu popout.

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
- **Silent Daily Audits**: Runs daily background checks without filling your modmail when everything is current.
- **Unified Moderator Menu Popout**: Open **App Update Checker** from either the subreddit menu or any post overflow menu (`...`) across desktop, mobile, and tablet to access:
  - **Check for App Updates**: Run an immediate scan and receive a full status report in Modmail.
  - **Sync All Apps as Updated**: Lock in current versions as the baseline after updating apps in Mod Tools.
  - **Reset App Cache**: Clear cached data and trigger a fresh discovery scan.
- **Native Settings Control**: Specify custom app slugs to monitor, toggle unlisted bot reporting, and configure check schedules in App Settings.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/app-update-checker-flowchart.png)

### Your Four-Step Lifecycle

1. **Discover**: App Update Checker discovers installed Devvit applications from subreddit bot signatures and configured custom slugs.
2. **Setup & Sync**: Make sure to update all your apps via Reddit's **Mod Tools > Installed Apps**, then run **Sync All Apps as Updated** in the menu popout.
3. **Silent Audit**: Runs automated daily checks at 12:00 UTC, comparing active community tools against version feeds compiled by our backend directory scraper.
4. **Notify**: Delivers an actionable Modmail alert only when an app author publishes a new release.

---

## Quick Setup

1. **Install**: Add **App Update Checker** to your subreddit through the Reddit App Directory.
2. **Update Apps in Mod Tools**: Open **Mod Tools > Installed Apps** in Reddit and update any outdated applications.
3. **Sync Baseline**: Open the subreddit menu (`...`), select **App Update Checker**, and choose **Sync All Apps as Updated** to establish your confirmed tracking baseline.
4. **Relax**: Scheduled daily audits will silently keep your team informed of any future releases.

*No manual app directory checking. Automated update notifications delivered directly to modmail.*

---

## Advanced Capabilities

App Update Checker is engineered for resilient version resolution and lightweight background execution.

- **Automated Backend Directory Scraper**: An automated backend pipeline crawls and scrapes public listings on `developers.reddit.com/apps/...` to maintain a continuously updated version dataset (`latest_versions.json`).
- **Redis-Cached Feed Delivery**: The directory snapshot is fetched from `raw.githubusercontent.com` and cached in Redis for fast, lightweight checks within platform limits.
- **Deterministic Semver Comparison**: Standard semver parsing reliably detects patch, minor, and major version increments without false positives.
- **Scheduled Cron Runner**: Executes automated checks on a daily cron schedule at 12:00 UTC.
- **Modmail Markdown Formatter**: Formats clean markdown tables with direct links to app install pages.

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
