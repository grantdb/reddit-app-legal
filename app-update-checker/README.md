# App Update Checker

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Utility](https://img.shields.io/badge/Category-Infrastructure-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Monitoring-8A2BE2?style=for-the-badge)

**App Update Checker** is a utility designed to help moderation teams effortlessly monitor all third-party Devvit applications installed in their community. Instead of manually checking for updates, it proactively scans your installed apps for new versions and sends automated alerts directly to your ModMail.

## Key Features

- **Automated Discovery**: Automatically queries the Devvit app directory to identify and track all third-party applications currently active on your subreddit.
- **Patch Detection**: Recognizes when developers release new versions, updates, or bug fixes for the apps you rely on.
- **ModMail Alerts**: Eliminates the need to monitor external changelogs by delivering actionable update notifications straight to the moderation team's inbox.
- **Precise Control**: Allows you to specifically include or exclude certain applications from being tracked if you prefer to manage them manually.

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/app-update-check-flowchart.png)

1. The app runs a background task on a scheduled interval.
2. It retrieves the list of installed apps on the subreddit and compares their currently installed versions against the latest available versions in the app registry.
3. If an update is detected, it formats a notification detailing the app name and version gap.
4. The notification is securely dispatched to the subreddit's ModMail to alert the team.

## Setup & Configuration

1. **Install**: Add **App Update Checker** to your subreddit via the App Directory.
2. **App Settings**: Navigate to your subreddit's Mod Tools > App Settings > App Update Checker.
3. **Configure Tracking**: Use the settings interface to specify if there are any installed apps you wish to exclude from monitoring.
4. **Monitoring**: The app will run automatically in the background. Simply keep an eye on ModMail for future update alerts.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/app-update-checker/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/app-update-checker/PRIVACY.md)

---
*Built for Reddit's moderator community.*

