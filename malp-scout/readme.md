> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/malp-scout)

# MALP-Scout

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Focus](https://img.shields.io/badge/Focus-Stargate_SG--1-blue?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Moderator_Only-success?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Content_Scout-8A2BE2?style=for-the-badge)

**MALP-Scout** is a manual-only Stargate SG-1 content scouting tool for subreddit moderators. Styled after the Stargate Reconnaissance Probe (MALP - Mobile Analytic Laboratory Probe), the app operates on demand using a local curated SG-1 dataset as its primary source of truth. It allows moderators to generate, preview, and selectively post high-quality, template-driven SG-1 content without remote web crawling, background schedulers, or automatic posting.

## Key Features

- **Manual On-Demand Reconnaissance**: Triggered strictly by subreddit moderators via the Mod Menu (`MALP: Launch Reconnaissance`). Zero automatic posting or background schedulers.
- **Local Curated SG-1 Knowledge Base**: Built-in, hand-reviewed dataset mapping SG-1 main/recurring cast birthdays, notable episode air dates, and major show milestones.
- **Strict Zero-Crossover Policy**: Enforces strict SG-1-only filtering, excluding Stargate Atlantis (SGA) and Stargate Universe (SGU) crossover content.
- **Importance Quality Floor**: Allows moderators to select a quality threshold (High, Medium, Low). Returns fewer candidates if not enough items meet the quality floor—never pads with weak filler.
- **Moderator Preview & Approval Gate**: Presents candidate titles, quality ranks, and 200-character excerpts in a confirmation form before any post is created on the subreddit.

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/malp-scout-flowchart.png)

1. A moderator initiates a scout run from the Subreddit Mod Menu or Post overflow menu (**MALP: Launch Reconnaissance**).
2. The scout engine evaluates active records in `sg1_curated_knowledge.json`, scores candidates, applies secondary SGA/SGU exclusion filters, and builds deterministic markdown templates.
3. Candidates are presented in a unified Devvit preview & edit form for moderator review.
4. Upon moderator confirmation, the approved candidate is published as a standard text post to the subreddit by the App Account.

## Setup & Configuration

1. **Install**: Add **MALP-Scout** to your subreddit via the Devvit App Directory.
2. **Usage**: Open the Subreddit Mod Menu (desktop) or tap the 3-dots on any post menu (mobile) and select **MALP: Launch Reconnaissance**.
3. **Select & Edit**: Pick your preferred candidate post, customize the title or body markdown if desired.
4. **Publish**: Tap **Publish Post Now** to submit to the subreddit.

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/malp-scout/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/malp-scout/PRIVACY.md)

---
*Built for Reddit's moderator community.*
