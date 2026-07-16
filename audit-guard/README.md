# GuardHub: Audit Guard 🛡️

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Logging-8A2BE2?style=for-the-badge)

**Audit Guard** is the automated audit logging and change tracking engine for the GuardHub ecosystem. In high-volume or highly sensitive communities, it is essential to have an immutable record of moderation events and system configurations. Audit Guard serves as the central nervous system for observing and recording exactly what actions were taken, by whom, and when.

## Key Features

- **Automated Logging**: Silently tracks key moderation events, automated enforcements, and configuration changes across all connected GuardHub applications.
- **Change Tracking**: Maintains an accessible, chronological history for moderation teams, ensuring full transparency and accountability for system adjustments.
- **Data Integrity**: Provides a reliable source of truth when debugging complex automod behaviors or auditing team activity.
- **Native Integration**: Seamlessly communicates with other GuardHub apps to ingest event data securely without exposing sensitive information.

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/audit-guard-flowchart.png)

1. Any connected GuardHub application executes an action, or a moderator changes a configuration setting.
2. The relevant app sends a secure telemetry signal to Audit Guard.
3. Audit Guard ingests, normalizes, and appends the event to a permanent chronological ledger.
4. Moderators can later review this ledger securely via the GuardHub Dashboard to trace the exact lineage of an enforcement action or config change.

## Setup & Configuration

1. **Install**: Add **Audit Guard** to your subreddit via the App Directory.
2. **Dashboard Initialization**: Navigate to your subreddit's Mod Tools and open the GuardHub Audit Guard Dashboard.
3. **Integration**: Audit Guard works passively in the background. Once installed, it will automatically begin listening for signals from your other active GuardHub applications.
4. **Usage**: Access the historical logs via the native Custom Post Dashboard inside your subreddit.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/audit-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/audit-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
