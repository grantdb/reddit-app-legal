> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/verify-guard)

# GuardHub: Verify Guard 🛡️

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Hardened-red?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Security-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Verification_Engine-8A2BE2?style=for-the-badge)

> **Streamline community verification, grant trust badges, and protect member privacy.**

Verify Guard provides a privacy-first verification and access engine for your subreddit. Manage multi-tier verification policies—including automated account trust gates, self-declared age gates, and manual role reviews—to award user flairs and approved contributor status without modmail clutter.

---

## At a Glance

- **Multi-tier verification**: Support automated trust gates, self-declared age gates, and manual mod review.
- **Interactive verification post**: Allow community members to verify directly from an interactive custom post.
- **Automate flair & access**: Automatically assign verified user flairs and approved contributor permissions.
- **Unified moderator controls**: Access dashboard webviews and post launcher creation from a single **VerifyGuard** menu popout.
- **Privacy-first design**: Zero storage of raw legal IDs, birthdates, or private personal data.
- **Automated expiration**: Automatically expire time-limited verifications and clean up user flairs via cron jobs.

---

## The Old Way vs. The Verify Guard Way

| Traditional Workflow | With Verify Guard |
| :--- | :--- |
| Sifting through flooded modmail threads for verification requests | **Dedicated interactive verification post** and intake review queue |
| Manually checking account age and karma for every applicant | **Automated Tier 1 health gates** verifying eligible users instantly |
| Storing sensitive verification photos in unsecure modmail archives | **Privacy-safe short-lived forms** automatically deleted upon review |
| Manually tracking and revoking expired verification badges | **Automated background cleanup** revoking flairs when verifications expire |
| Mod team losing track of who reviewed an applicant | **Structured audit logs** recording reviewer decisions and timestamps |

---

## Built for Trust and Privacy

- **Tier 1: Automated Trust Gates**: Automatically verify accounts that meet minimum account age, karma thresholds, and safety criteria.
- **Tier 2: Self-Declared Age Gates**: Verify community age-band eligibility (18+ / 21+) with privacy-first boolean confirmations.
- **Tier 3: Role & Expert Review**: Custom intake questionnaire with a secure moderator review dashboard for AMA guests and expert badges.
- **Custom Post Verification Center**: Launch an unlisted or pinned verification post where community members initiate intake.
- **Automated Lifecycle Expiration**: Scheduled background maintenance automatically revokes expired badges and updates user permissions.
- **Unified Moderator Menu Popout**: Select **VerifyGuard** from the subreddit overflow menu (`...`) to access:
  - **Open Verification Dashboard**: Launch the React Webview triage center to configure policies, inspect logs, and review pending requests.
  - **Create Verification Post**: Submit an interactive user intake launcher post directly to your subreddit.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/verify-guard-flowchart.png)

### Your Four-Step Workflow

1. **Initiate**: A community member opens the interactive Verification Center post.
2. **Evaluate**: Automated Tier 1 trust gates verify qualifying accounts instantly, while Tier 3 applications route to the mod queue.
3. **Approve**: Moderators review pending intake requests in the dashboard with one-click approval or denial.
4. **Grant**: On approval, Verify Guard assigns the configured user flair and grants contributor permissions.

---

## Quick Setup

1. **Install**: Add **Verify Guard** to your subreddit through the Reddit App Directory.
2. **Launch Dashboard**: Open the subreddit menu (`...`), select **VerifyGuard**, and choose **Open Verification Dashboard**.
3. **Launch Post**: Open **VerifyGuard** and choose **Create Verification Post** to generate your community intake post.
4. **Activate**: Set your desired verification tiers in the dashboard to begin welcoming verified members.

*No modmail clutter or sensitive data exposure. Streamlined community verification directly in Reddit.*

---

## Advanced Capabilities

Verify Guard is engineered for high-concurrency member verification with strict data privacy guarantees.

- **Partitioned Redis Hash Storage**: Organizes user verification profiles into partitioned hash buckets (`gh:vg:prof:<subId>:<bucketId>`) to prevent key sprawl.
- **Ephemeral Intake Lifecycles**: Applies automatic TTL expirations (48–72h) to intake submissions, hard-deleting answers upon review.
- **Automated Revocation Cron**: Executes scheduled daily background tasks to prune expired verification profiles and sync flair states.
- **Interactive React Webview**: Provides an intuitive intake wizard for users and a triage dashboard for moderators.

---

## Designed to Assist Moderators

Verify Guard automates verification intake and policy evaluation according to the exact tiers defined by your moderation team. Tier evaluations and intake responses serve as assistive tools—human moderators maintain complete authority to approve, deny, override, or revoke verification statuses at any time.

---

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

---

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/verify-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/verify-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
