Suspended Remover
Category: Security
Version: v1.0.80
Visibility: Public
Summary: High-precision account purification engine. Fleet-wide security infrastructure.

Overview
High-precision account purification engine. Fleet-wide security infrastructure.

Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/suspended-remove-flowchart.png)

Key Features
- Not documented yet.

Permissions Used
- redis: Redis key-value storage (state tracking, caching, strike memory)

Triggers and Activation
Event Triggers
- AppInstall: Subscribed in main.ts via Devvit.addTrigger({ event: 'AppInstall' }).
- AppUpgrade: Subscribed in main.ts via Devvit.addTrigger({ event: 'AppUpgrade' }).

Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

Settings Reference
- enabled (boolean, default: true): Enable automated enforcement - Turn this off to pause all scan actions without uninstalling the app.
- recheckDays (number, default: -): Days between rechecks - Default: 0 for legacy behavior and lowest rollout friction. Use 0 to allow
- confirmChecks (number, default: -): Required verification checks - Default: 1 for legacy behavior and lowest rollout friction. Increase this if
- duringWaitAction (select, default: -): What to do during the waiting window - What to do during the waiting window
- addDuringWaitNote (boolean, default: -): Add mod note to item during waiting window - Adds the waiting-period note to the item when the waiting action is applied.
- duringWaitReason (string, default: -): Waiting-period mod note text - This note is added to the item when the waiting-period action is applied.
- approveRecoveredTempRemovals (boolean, default: -): Auto-approve if account recovers (hidden/temp-removed items) - If a later check shows the account is accessible again, the app will automatically approve
- finalAction (select, default: -): Final action after threshold - Final action after threshold
- markAsSpam (boolean, default: -): [Deprecated] Mark final removal as spam - This older setting is still shown for compatibility with existing installs.
- addFinalNote (boolean, default: -): Add mod note to item on final action - Adds the final-action note to the item when it is removed. Turn this off if
- finalReason (string, default: Suspended): Final-action mod note text - This note is added to the item when the final action is applied.
- addUserNote (boolean, default: -): Add mod note to user on final action - Adds a note to the user
- userNoteLabel (select, default: -): User note label - User note label
- userNoteText (string, default: Account): User note text - User note text
- legalDocs (string, default: See): Terms & Privacy - Terms & Privacy
- scanModqueueJob (all, default: -): GuardHub: Scan Modqueue for Suspended Users - GuardHub: Scan Modqueue for Suspended Users

Automation Capabilities
- Submits Automated Comments: No
- Attaches Removal Notes: Yes
- Approves Content: Yes
- Removes or Filters Content: Yes
- Dispatches Modmail Alerts: No
- Updates User or Post Flair: No

Data Storage
This app utilizes Reddit Redis storage:
- Key-Value Strings (deduplication & cooldown markers)
- Hashes (structured records & alias indices)

Setup and Usage
- Install: Add Suspended Remove to your subreddit through the Reddit App Directory.
- Configure Pipeline: Open Mod Tools > App Settings > Suspended Remove.
- Choose Waiting Mode: Select your preferred waiting-stage action (*Filter & Hide* recommended).
- Save: Background queue scanning activates immediately with zero manual maintenance.
- No more orphaned mod queue items. Clean, safe queue automation directly inside Reddit.*

Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.

Version History
1.0.80 — 2026-08-16
- Fix: Removed duplicate manifest menu declaration in `devvit.json` to resolve double menu trigger in subreddit moderator tools.
1.0.79 — 2026-08-15
- Standard fleet synchronization and maintenance.
1.0.78 — 2026-08-15
- Standard fleet synchronization and maintenance.

Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/suspended-remove/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/suspended-remove/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/suspended-remove)