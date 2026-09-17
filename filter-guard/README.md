> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/filter-guard)

# GuardHub: Filter Guard 🛡️

> **Combine complex participation rules into simple, reliable community gates.**

Filter Guard equips moderation teams with layered threshold logic without cryptic syntax. Combine account age, karma requirements, and risk scores using visual AND/OR gates, test everything safely in an interactive simulator, and manage all your filter policies through a private dashboard.

### ⚡ Key Highlights
- **Layered Multi-Factor Gates**: Combine account age, combined karma, post karma, comment karma, and safety scores into unified rules.
- **Visual AND/OR Logic**: Require all conditions to match (AND) or trigger on any single failed threshold (OR).
- **Interactive Test Sandbox**: Safely dry-run rules against any Reddit username inside the dashboard before turning them live.
- **Repeat Offender Escalation**: Automatically track repeated filter triggers across 7-day windows and dispatch alerts to modmail.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/filter-guard-flowchart.png)

### The Four-Step Lifecycle

1. **Receive**: Filter Guard intercepts new posts and comments in real time as they arrive in your subreddit.
2. **Evaluate**: The submitting author's age, karma breakdown, and risk score are measured against active Rule Groups.
3. **Process**: Configurable AND/OR logic gates evaluate compound criteria to determine whether the submission qualifies.
4. **Action**: If thresholds fail, the configured moderation action (`filter`, `remove`, `spam`, or `report`) is applied immediately with structured audit logging.

---

## Quick Setup

1. **Install**: Add **Filter Guard** to your subreddit through the Reddit App Directory.
2. **Open Dashboard**: Access the **GuardHub: FilterGuard Dashboard** from your Subreddit Mod Tools.
3. **Configure Gates**: Define your threshold groups and test them against candidate users in the Test tab.
4. **Enforce**: Activate your verified rule groups to start automated community gating.

*No complex YAML syntax required. Clean layered protection managed directly from your native dashboard.*

---

## Core Capabilities

- **Multi-Condition Rule Groups**: Combine account age, combined karma, post karma, and comment karma into cohesive gatekeeper policies.
- **AND/OR Decision Logic**: Configure flexible criteria—require all conditions to pass or allow any single threshold to qualify.
- **Author Risk Score Gating**: Factor calculated account safety signals into your threshold checks to isolate suspicious submissions.
- **Rolling Repeat Escalation**: Automatically count repeated filter hits over 7 days and dispatch summary alerts to modmail.
- **Interactive Simulator**: Test rule groups against candidate usernames inside the dashboard before turning them live.
- **Dedicated Moderator Dashboard**: Open a private dashboard from Subreddit Mod Tools to inspect metrics, adjust gates, and monitor activity.

---

## The Old Way vs. The Filter Guard Way

| Traditional Workflow | With Filter Guard |
| :--- | :--- |
| Writing complex, nested AutoMod rules that conflict with each other | **Visual rule groups** with clear, predictable AND/OR logic |
| Testing multi-factor rules blindly on live subreddit users | **Interactive Test tab** to simulate rules against real usernames |
| Manually tracking repeat offenders triggering filters | **Automated strike tracking** across a 7-day rolling window |
| Mod team confused by why a multi-condition rule failed | **Structured decision logs** showing which exact condition triggered |

---

## Designed to Assist Moderators

Filter Guard automates the evaluation of multi-factor participation gates based on the criteria configured by your moderation team. Threshold results serve as assistive moderation tools—human moderators retain full authority to review filtered content in mod queue, approve exceptions, and adjust policy sensitivity at any time.

---

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/filter-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/filter-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
