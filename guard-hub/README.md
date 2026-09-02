> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/guard-hub)

# GuardHub: Guard Hub 🛡️

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Hardened-red?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Administration-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Administration-8A2BE2?style=for-the-badge)

> **Monitor, coordinate, and inspect your entire GuardHub moderation defense system from one central hub.**

Guard Hub is the unified control center and observability dashboard for the GuardHub moderation ecosystem. Monitor installed guard modules, detect configuration drift, check defense layer health, and inspect cross-app audit telemetry—all from a single native dashboard inside your subreddit.

---

## At a Glance

- **Unified defense overview**: View the active operational status of all installed GuardHub modules at a glance.
- **System health monitoring**: Identify disabled modules, misconfigured thresholds, or coverage gaps automatically.
- **Cross-app audit gateway**: Inspect aggregated moderation metrics and telemetry across your entire suite.
- **Zero-friction setup**: Automatically discovers sibling GuardHub apps installed in your subreddit.
- **Secure moderator hub**: Access your central control panel directly from Subreddit Mod Tools.

---

## The Old Way vs. The Guard Hub Way

| Traditional Workflow | With Guard Hub |
| :--- | :--- |
| Opening 10 separate app settings pages to check module statuses | **Single-pane-of-glass overview** showing all active defense layers |
| Wondering if an important filter bot was accidentally turned off | **Automated health checks** alerting you to disabled guardrails |
| Piecing together audit trails across disconnected tools | **Unified telemetry gateway** aggregating cross-app activity |
| Manually tracking which version of each mod tool is installed | **Centralized suite inventory** displaying module versions and status |
| Uncoordinated moderation rules causing conflicting actions | **Cohesive system monitoring** ensuring defense layers align cleanly |

---

## Built for Unified Moderation Control

- **Unified Defense Observability**: Monitor real-time status across Domain Guard, Filter Guard, User Guard, Queue Guard, and sibling modules.
- **Automated Health Engine**: Detects inactive tools, missing permissions, or configuration inconsistencies before they impact community moderation.
- **Centralized Telemetry Gateway**: Aggregates high-level enforcement metrics and links directly into Audit Guard logs for deep inspection.
- **Zero-Configuration Discovery**: Automatically detects and surfaces sibling GuardHub apps without requiring complex manual linking.
- **Streamlined Team Oversight**: Provides lead moderators with immediate visibility into automated enforcement activity across the community.
- **Dedicated Management Center**: Access a native dashboard from Subreddit Mod Tools on both desktop and mobile.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/guard-hub-flowchart.png)

### Your Four-Step Workflow

1. **Discover**: Guard Hub scans your subreddit to detect all installed and active GuardHub modules.
2. **Collect**: Lightweight operational telemetry and status signals are gathered from active defense layers.
3. **Analyze**: The health engine verifies system integrity, active rule coverage, and operational readiness.
4. **Display**: Moderators review suite status, active defense health, and aggregated metrics in the central dashboard.

---

## Quick Setup

1. **Install**: Add **Guard Hub** to your subreddit through the Reddit App Directory.
2. **Open Hub**: Launch **GuardHub: Guard Hub Dashboard** from Subreddit Mod Tools.
3. **Review**: Guard Hub automatically discovers your installed apps and displays your community defense status.
4. **Monitor**: Check the dashboard periodically to ensure all moderation layers remain fully operational.

*No complex configuration required. Complete observability for your entire moderation ecosystem.*

---

## Advanced Capabilities

Guard Hub is engineered for lightweight status aggregation and comprehensive suite monitoring.

- **Suite Discovery Engine**: Interrogates subreddit app installations and configuration states via native Devvit APIs.
- **Integrity Health Matrix**: Evaluates active modules against recommended community protection baselines.
- **Cross-Module Telemetry Aggregator**: Collects lightweight event summaries without impacting queue processing performance.
- **Native Webview Interface**: Renders an interactive React overview of suite health and quick navigation links.

---

## Designed to Assist Moderators

Guard Hub provides centralized status monitoring and defense layer observability across your installed moderation apps. Health signals and metrics serve as operational guidance—human moderators maintain complete authority over app configurations, rule definitions, and community policies.

---

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

---

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/guard-hub/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/guard-hub/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
