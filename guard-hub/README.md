# GuardHub: Guard Hub 🛡️

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Administration-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Administration-8A2BE2?style=for-the-badge)

**Guard Hub** is the central administration and monitoring umbrella for the entire GuardHub moderation family. Instead of managing dozens of disconnected apps, it provides community leaders with a unified, single-pane-of-glass view of their automated defense layers, performance metrics, and configuration states across the subreddit.

## Key Features

- **Unified Observability**: Provides high-level status monitoring for all installed Guard family applications (Domain Guard, Filter Guard, etc.) from a single dashboard.
- **System Integrity Checks**: Proactively detects configuration drift, disabled modules, or outdated app versions that could leave your community vulnerable.
- **Centralized Logging**: Acts as a gateway to your Audit Guard ledgers, providing a single entry point for auditing moderation actions across the entire fleet.
- **Private Dashboard**: A fully secure, moderator-only control panel accessible natively on Reddit via mobile or desktop.

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/guard-hub-flowchart.png)

1. All installed GuardHub applications send lightweight telemetry regarding their operational status (e.g., active, disabled, error states).
2. Guard Hub aggregates this data alongside high-level metrics from your Audit Guard logs.
3. The Health Engine evaluates the ecosystem's integrity. If a critical app is disabled, it flags an alert.
4. Moderators review the ecosystem's health via the central Guard Hub Dashboard.

## Setup & Configuration

1. **Install**: Add **Guard Hub** to your subreddit via the App Directory. (Note: It works best when other GuardHub apps are already installed).
2. **Dashboard Initialization**: Navigate to your subreddit's Mod Tools and open the GuardHub: Guard Hub Dashboard.
3. **Usage**: Use the dashboard to monitor the status of your community defense layers. No complex configuration is required as it automatically detects sibling apps.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/guard-hub/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/guard-hub/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
