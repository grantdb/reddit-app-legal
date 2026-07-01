# GuardHub - Duplicate Guard 🛡️

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Hardened-red?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blueviolet?style=for-the-badge)

## Purpose
Duplicate Guard is a subreddit moderation app that checks new posts for likely duplicate subjects or topics. When a new post is submitted, it compares the title against recent posts in your subreddit and flags or removes reposted discussion topics and slightly reworded duplicate submissions. 

*Note: This app does not check for duplicate URLs or domain matching. For URL checking, use DomainGuard.*

## Features
- **Configurable Match Modes**: Choose between strict exact matches or more balanced algorithmic matching that detects slightly reworded titles.
- **Adjustable Windows**: Configure how many recent posts or days to look back for duplicates.
- **Fail-Safe Operation**: Built with strict effectively-once guarantees so duplicate platform events will never result in duplicate moderation actions.
- **Moderator Controls**: Easily exempt moderators, approved users, or specific flairs from being checked.

## Install / Use
1. Install Duplicate Guard on your subreddit from the App Directory.
2. Open your subreddit's App Settings and adjust the Match Mode (Strict, Balanced, or Aggressive).
3. The app will automatically run in the background and monitor new posts.

## Limitations & Future Ideas
- Currently relies primarily on title similarity and keyword overlap, without advanced semantic AI processing.
- Future versions may incorporate AI summary extraction and deeper semantic comparison.
- Cross-subreddit checks are currently unsupported.

## Settings
This app can be configured directly from the subreddit's App Settings menu.

## Legal
This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/duplicate-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/duplicate-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
