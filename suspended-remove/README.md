> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/suspended-remove)

# Suspended Remove

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Hardened-red?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Security-8A2BE2?style=for-the-badge)

> **Clean mod queue backlogs from suspended and shadowbanned accounts automatically.**

Suspended Remove safely clears content left behind by suspended, deleted, or shadowbanned accounts. Featuring a multi-stage verification pipeline with customizable waiting actions (Filter & Hide, Filter & Keep Public, or Temp Remove) and auto-recovery, it keeps your mod queue clean while protecting false flags.

---

## At a Glance

- **Two-stage verification**: Hold suspected items during a confirmation window before applying permanent removal.
- **Three waiting-stage modes**: Choose between Filter & Hide, Filter & Keep Public, or Temporary Remove.
- **Automated account recovery**: Automatically restore and approve content if an account becomes accessible again.
- **Detailed Mod Notes**: Attach custom internal mod notes and user profile notes at every stage of the check.
- **Background queue scanning**: Continuously scans posts and comments across modqueue and spam folders.

---

## The Old Way vs. The Suspended Remove Way

| Traditional Workflow | With Suspended Remove |
| :--- | :--- |
| Clicking on inaccessible user profiles and guessing why they failed | **Automated API status verification** identifying shadowbans and suspensions |
| Mod queue permanently cluttered with orphaned posts | **Scheduled background cleanup** clearing unresolvable content |
| Accidental removal of users experiencing temporary API outages | **Multi-stage confirmation checks** re-verifying accounts across multiple days |
| Manually restoring posts when a user successfully appeals a ban | **Auto-recovery engine** automatically re-approving restored accounts |
| Wondering why a post was removed weeks later | **Structured Mod Notes** recording check timestamps and status reasons |

---

## Built for Queue Hygiene & Safe Verification

- **Two-Stage Enforcement**: Protects innocent users with a configurable waiting period before executing permanent removals.
- **Customizable Waiting Actions**:
  - *Filter & Hide*: Pulls items from public view into Needs Review while checks run.
  - *Filter & Keep Public*: Keeps items visible on the subreddit while tracking them in Needs Review.
  - *Temporary Remove*: Moves items to the removed queue during multi-day checks.
- **Automatic Account Recovery**: If an account is unsuspended or verified accessible on a subsequent check, Suspended Remove can automatically approve the item.
- **Granular Mod Notes**: Independently toggle and customize internal mod notes attached during the waiting stage and final removal.
- **Automated Retention Capping**: Items in the verification pipeline are automatically expired and pruned after 14 days.
- **Native Settings Control**: Configure confirmation check counts, waiting modes, and removal actions directly in Subreddit Mod Tools.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/suspended-remove-flowchart.png)

### Your Four-Step Workflow

1. **Scan**: Suspended Remove scans posts and comments across your subreddit's modqueue and spam queue.
2. **Verify**: The engine tests author profile accessibility against the Reddit User API.
3. **Hold**: On the first confirmed inaccessibility, your chosen waiting-period action (*Filter & Hide*, *Filter & Keep Public*, or *Temp Remove*) is applied.
4. **Action or Recover**: If the account remains inaccessible after all scheduled checks, the final action executes; if the account recovers, the post is automatically approved.

---

## Quick Setup

1. **Install**: Add **Suspended Remove** to your subreddit through the Reddit App Directory.
2. **Configure Pipeline**: Open **Mod Tools > App Settings > Suspended Remove**.
3. **Choose Waiting Mode**: Select your preferred waiting-stage action (*Filter & Hide* recommended).
4. **Save**: Background queue scanning activates immediately with zero manual maintenance.

*No more orphaned mod queue items. Clean, safe queue automation directly inside Reddit.*

---

## Advanced Capabilities

Suspended Remove is engineered for resilient API status resolution and stateful multi-day queue tracking.

- **Account Accessibility Verifier**: Distinguishes between deleted accounts, shadowbanned users, and network timeouts.
- **Stateful Redis Queue**: Tracks pending items across configurable multi-day recheck schedules with atomic updates.
- **Auto-Recovery Restorer**: Re-evaluates queued items on subsequent crons and executes automated approvals upon profile restoration.
- **Mod Note Synchronizer**: Directly appends internal Reddit Mod Notes with customizable format templates.

---

## Designed to Assist Moderators

Suspended Remove verifies account accessibility to assist in queue hygiene and orphaned content management. Multi-stage checks and mod notes ensure transparency—human moderators retain full authority to review, approve, or adjust account verification settings at any time.

---

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include:
- The app name.
- What you expected to happen.
- What happened instead.
- Any error message.
- Screenshots or relevant details.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/suspended-remove/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/suspended-remove/PRIVACY.md)

---
*Built for Reddit's moderator community.*
