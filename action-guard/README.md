> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/action-guard)

# GuardHub: Action Guard 🛡️

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Hardened-red?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Automation_Engine-8A2BE2?style=for-the-badge)

> **Automate multi-step moderation playbooks and coordinate team enforcement in one click.**

Action Guard is the workflow automation and response orchestrator for your subreddit. Trigger multi-action moderation playbooks—combining removals, temporary mutes, flair updates, thread locks, and mod notes—from a single event or menu trigger, managed visually from your private control center.

---

## At a Glance

- **Multi-action playbooks**: Execute combined actions (e.g. remove, lock, flair, and note) in a single sequence.
- **Event-driven triggers**: Respond automatically to new posts, comments, or specific moderator operations.
- **Identity & flair sync**: Apply automated user and post flairs to record enforcement states transparently.
- **Safe Dry-Run Mode**: Test complex action sequences with simulated logs before deploying live.
- **Visual dashboard management**: Configure and test all orchestration rules from a secure moderator dashboard.

---

## The Old Way vs. The Action Guard Way

| Traditional Workflow | With Action Guard |
| :--- | :--- |
| Manually performing 4 separate steps (remove, lock, flair, note) | **Automated multi-action playbooks** executing the entire sequence at once |
| Mod team members using inconsistent enforcement steps | **Standardized action recipes** ensuring 100% consistent team handling |
| Juggling external bot scripts to chain moderation events | **Native Devvit trigger engine** running securely inside Reddit |
| Testing automated playbooks directly on active community members | **Dry-Run Mode** verifying actions in simulated logs first |
| Losing track of which rule triggered a multi-step moderation event | **Structured execution audit logs** detailing every step taken |

---

## Built for Coordinated Moderation

- **Orchestration Playbooks**: Chain together removals, locks, flairs, mutes, and internal notes into automated response recipes.
- **Event-Driven Automation**: Trigger workflows on post creation, comment submissions, or upstream mod actions.
- **Status & Flair Synchronization**: Automatically update user and submission flairs to reflect current moderation status.
- **Safe Testing Sandbox**: Run playbooks in Dry-Run Mode to simulate execution and review logs before turning on live enforcement.
- **Modmail Notifications**: Format and deliver summary alerts to your team modmail thread when high-priority playbooks fire.
- **Dedicated Orchestrator Center**: Access a private dashboard from Subreddit Mod Tools to build playbooks, test triggers, and inspect history.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/action-guard-flowchart.png)

### Your Four-Step Workflow

1. **Trigger**: Action Guard intercepts a submission, comment event, or moderator action.
2. **Evaluate**: The event is matched against active playbook criteria and priority rules.
3. **Execute**: Action Guard fires the configured action sequence (e.g. `Remove` + `Lock` + `Apply Flair` + `Add Mod Note`).
4. **Log**: All executed actions and dry-run simulations are recorded in the dashboard audit log.

---

## Quick Setup

1. **Install**: Add **Action Guard** to your subreddit through the Reddit App Directory.
2. **Configure**: Open **GuardHub: ActionGuard Orchestrator** from Subreddit Mod Tools.
3. **Create Playbooks**: Build your multi-action response recipes and test them in Dry-Run Mode.
4. **Activate**: Switch verified playbooks to Live mode to begin automated orchestration.

*No external bot hosting required. Coordinated multi-action workflows directly within Reddit.*

---

## Advanced Capabilities

Action Guard is engineered for reliable, sequential action execution and high-concurrency event routing.

- **Sequential Action Pipeline**: Executes multi-step moderation operations in deterministic order with individual step error handling.
- **Event Dispatch Router**: Handles `onPostCreate`, `onCommentCreate`, and `onModAction` trigger streams through unified handlers.
- **Dry-Run Execution Engine**: Simulates API calls and generates detailed mock logs without applying destructive changes to Reddit state.
- **Redis Playbook Store**: Persists JSON-encoded playbook definitions and execution logs with atomic state updates.

---

## Designed to Assist Moderators

Action Guard coordinates and automates moderation workflows according to the exact playbooks defined by your moderation team. Automated actions follow strict rules established by human moderators, who maintain full authority to review, override, and modify playbook behaviors at any time.

---

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

---

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/action-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/action-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
