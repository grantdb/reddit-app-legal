# GuardHub: Domain Guard 🛡️

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Security-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Content_Policy-8A2BE2?style=for-the-badge)

**Domain Guard** is a professional-grade URL moderation engine built specifically for Reddit. It empowers moderators to enforce strict domain policies, completely block malicious or spam-heavy link farms, and maintain community integrity—all managed through an intuitive, native control dashboard rather than complex AutoModerator regex.

## Key Features

- **Granular Domain Rules**: Define strict allowlists (only these sites are allowed) or blocklists (these sites are banned) using advanced but easy-to-use hostname matching.
- **Context-Aware Scopes**: Apply your URL rules globally, or restrict them specifically to Link Submissions, Text Post Bodies, or Comment text.
- **Safe Testing Mode**: Built-in "Audit Mode" allows you to safely test new domain rules in the background and review logs before enforcing them live on your users.
- **Private Dashboard**: A fully secure, moderator-only Custom Post Dashboard for managing your policies without needing to touch code.

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/domain-guard-flowchart.png)

1. A user submits a post or comment containing a hyperlink.
2. Domain Guard extracts the hostname and checks it against your active policy lists.
3. Depending on the rule and scope, the app will either remove the content, approve it, or (if in Audit Mode) simply log the match for moderator review.

## Setup & Configuration

1. **Install**: Add **Domain Guard** to your subreddit via the App Directory.
2. **Dashboard Initialization**: Navigate to your subreddit's Mod Tools and open the GuardHub: Domain Guard Dashboard.
3. **Configure Rules**: 
   - Navigate to the Rules tab to create your first domain policy.
   - We recommend starting rules in "Audit" mode to ensure they don't catch legitimate links.
4. **Enforce**: Once you confirm the rule works via the Test tab, switch it to "Live" mode.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/domain-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/domain-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
