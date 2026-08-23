> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/filter-guard)

# GuardHub: Filter Guard 🛡️

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Hardened-red?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Gatekeeper-8A2BE2?style=for-the-badge)

> **Combine complex participation rules into simple, reliable community gates.**

Filter Guard gives moderation teams layered threshold logic without cryptic syntax. Combine account age, karma requirements, and risk score criteria using clear AND/OR gates, test everything safely in a visual simulator, and manage all your filter policies through a private dashboard.

---

## At a Glance

- **Combine multiple conditions**: Build rules requiring multiple criteria simultaneously (e.g. account age AND comment karma).
- **Flexible logic gates**: Use clear AND/OR decision trees for fine-grained community protection.
- **Risk score integration**: Include dynamic 0–100 author safety signals directly in threshold evaluations.
- **Automated escalations**: Track repeat threshold triggers across 7-day windows and notify modmail.
- **Visual dashboard management**: Configure and test all filter groups without editing code or YAML files.

---

## The Old Way vs. The Filter Guard Way

| Traditional Workflow | With Filter Guard |
| :--- | :--- |
| Writing complex, nested AutoMod rules that conflict with each other | **Visual rule groups** with clear, predictable AND/OR logic |
| Testing multi-factor rules blindly on live subreddit users | **Interactive Test tab** to simulate rules against real usernames |
| Manually tracking repeat offenders triggering filters | **Automated strike tracking** across a 7-day rolling window |
| Applying rigid subreddit-wide rules with no flexible branching | **Layered threshold groups** tailored to specific content contexts |
| Mod team confused by why a multi-condition rule failed | **Structured decision logs** showing which exact condition triggered |

---

## Built for Layered Protection

- **Multi-Condition Rule Groups**: Combine account age, combined karma, post karma, and comment karma into unified decision gates.
- **AND/OR Decision Logic**: Configure flexible criteria—require all conditions to pass or allow any single threshold to qualify.
- **Safety Score Gating**: Factor calculated account safety signals into your threshold checks to isolate suspicious submissions.
- **Rolling Repeat Escalation**: Automatically count repeated filter hits over 7 days and dispatch summary alerts to modmail.
- **Interactive Simulator**: Test rule groups against candidate usernames inside the dashboard before turning them live.
- **Dedicated Control Center**: Open a private dashboard from Subreddit Mod Tools to inspect metrics, adjust gates, and monitor activity.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/filter-guard-flowchart.png)

### Your Four-Step Workflow

1. **Receive**: Filter Guard intercepts new posts and comments as they are submitted to the subreddit.
2. **Evaluate**: The submitting author's age, karma breakdown, and risk score are measured against active Rule Groups.
3. **Process**: The AND/OR logic gate processes all conditions to determine whether the submission meets criteria.
4. **Action**: If thresholds fail, the configured action (`filter`, `remove`, `spam`, or `report`) is applied, and repeat counts update.

---

## Quick Setup

1. **Install**: Add **Filter Guard** to your subreddit through the Reddit App Directory.
2. **Configure**: Open **GuardHub: FilterGuard Dashboard** from Subreddit Mod Tools.
3. **Create Gates**: Define your threshold groups and test them in the Test tab.
4. **Enforce**: Activate your verified rule groups to start automated gating.

*No complex YAML syntax required. Clean layered protection managed directly from your dashboard.*

---

## Advanced Capabilities

Filter Guard is built for high-reliability rule evaluation across high-volume moderation queues.

- **Composite Condition Engine**: Evaluates compound logical expressions (AND / OR) across multiple account metrics in a single pass.
- **Rolling 7-Day Window Tracking**: Uses Redis counters to record repeat violation frequencies per user without manual tracking.
- **Simulated Test Harness**: Provides an in-dashboard sandbox to test live user profiles against active rule definitions.
- **Modmail Notification Dispatch**: Automatically formats and sends structured violation reports to modmail upon repeat threshold escalation.

---

## Designed to Assist Moderators

Filter Guard automates the evaluation of multi-factor participation gates based on the criteria configured by your moderation team. Threshold results serve as assistive moderation tools—human moderators retain full authority to review filtered content in mod queue, approve exceptions, and adjust policy sensitivity at any time.

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
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/filter-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/filter-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
