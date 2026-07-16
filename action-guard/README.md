# GuardHub: Action Guard 🛡️

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Automation_Engine-8A2BE2?style=for-the-badge)

**Action Guard** is the core automated enforcement engine of the GuardHub ecosystem. Instead of relying on manual actions, it centralizes and executes mass-moderation playbooks across your community based on triggers from other GuardHub applications. It serves as the automated "muscle" behind your subreddit's security network.

## Key Features

- **Orchestration Playbooks**: Automatically execute bans, mutes, post removals, and thread locks based on predefined rules. 
- **Identity Sync**: Dynamically applies user and post flairs to track reputation, status, and enforcement actions transparently.
- **Cross-App Triggers**: Listens for signals from other GuardHub apps (like Filter Guard or Domain Guard) to take decisive action instantly.
- **Private Dashboard**: Features a fully secure, moderator-only control panel rendered natively within Reddit for configuring rules and monitoring activity.

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/action-guard-flowchart.png)

1. Another application in your subreddit detects a violation and emits an alert signal.
2. Action Guard catches the signal and cross-references it with your configured Playbooks.
3. If the criteria are met, Action Guard executes the required moderation actions (banning, muting, or flairing) instantly.
4. All actions are logged and displayed in the secure moderator dashboard.

## Setup & Configuration

1. **Install**: Add **Action Guard** to your subreddit via the App Directory.
2. **Dashboard Initialization**: Navigate to your subreddit's Mod Tools and open the GuardHub Dashboard to initialize the app.
3. **Configure Playbooks**: Use the interactive Custom Post Dashboard to define your enforcement rules (e.g., "If User gets 3 Spam alerts, issue a 7-day ban").

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/action-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/action-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
