# GuardHub: Filter Guard 🛡️

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Gatekeeper-8A2BE2?style=for-the-badge)

**Filter Guard** is a grouped moderation app built for designing complex, threshold-based gating rules. While AutoModerator handles simple one-off checks, Filter Guard provides flexible, layered logic for community gates—allowing you to combine multiple safety and reputation thresholds into single, cohesive decision points.

## Key Features

- **Combined Thresholds**: Create advanced rules that require multiple conditions simultaneously (e.g., a user must have 100 comment karma AND their account must be 30 days old).
- **Flexible Gating Logic**: Supports complex AND/OR logic gating for threshold groups, giving you granular control over who can post or comment.
- **Integrated Safety Checks**: Leverage built-in safety thresholds to quickly block known spam rings or harassment patterns without writing complicated regex.
- **Private Dashboard**: Complete with a fully secure, moderator-only Custom Post Dashboard for managing your rule groups and testing logic.

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/filter-guard-flowchart.png)

1. A user attempts to post or comment in your community.
2. Filter Guard evaluates the user's attributes against your configured Rule Groups.
3. The logic gate processes the conditions (AND/OR). If a user fails the combined threshold logic, action is taken instantly.

## Setup & Configuration

1. **Install**: Add **Filter Guard** to your subreddit via the App Directory.
2. **Dashboard Initialization**: Navigate to your subreddit's Mod Tools and open the GuardHub: Filter Guard Dashboard.
3. **Configure Gates**: 
   - Use the Rules tab to create your first threshold group.
   - Mix and match account age, karma requirements, and safety signals.
4. **Testing**: Always verify your logic in the Test tab to see exactly how it would apply to a specific user before enforcing it live.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/filter-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/filter-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
