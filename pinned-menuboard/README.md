# Pinned Menuboard

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Utility](https://img.shields.io/badge/Category-Subreddit_Utility-blueviolet?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Community_Styling-8A2BE2?style=for-the-badge)

**Pinned Menuboard** is a dynamic community navigation hub that lives right inside your subreddit. It solves Reddit's restrictive two-pin limit by allowing moderators to curate a persistent, interactive "Menu Board" post that displays up to four featured posts or games in a clean, visual grid interface.

## Key Features

- **Clean Grid Layout**: Presents a beautiful, condensed 2x2 grid layout showing image thumbnails and titles for up to four featured posts, bypassing the standard two-sticky limitation.
- **Easy Management**: Add or remove featured posts instantly from the board by simply clicking a Mod Action directly on the target post—no URL copying or JSON editing required.
- **Instant Updates**: The Menuboard automatically and instantly refreshes itself as soon as moderators add or remove a featured post.
- **Custom Branding**: Easily customize the title of the menuboard post and its internal header text to match your community's theme.

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/pinned-menuboard-flowchart.png)

1. The mod team generates the master Pinned Menuboard post and sticks it to the top of the subreddit.
2. A moderator finds a high-quality user post (or an interactive app like a game) they want to feature and clicks "Toggle on Menuboard" in that post's Mod Menu.
3. The app verifies that there is an empty slot in the 2x2 grid.
4. The master Menuboard post instantly redraws itself to include the newly featured content's thumbnail and link.

## Setup & Configuration

1. **Install**: Add **Pinned Menuboard** from the App Directory.
2. **Dashboard Initialization**: Navigate to your subreddit's Mod Tools > App Settings > Pinned Menuboard to customize the titles.
3. **Usage**: 
   - Generate the master board via the Subreddit Mod Action menu ('Generate Pinned Menuboard').
   - Pin it to your subreddit.
   - Use the 'Toggle on Menuboard' Mod Action on any post to feature it.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/pinned-menuboard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/pinned-menuboard/PRIVACY.md)

---
*Built for Reddit's moderator community.*
