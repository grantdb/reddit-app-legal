# Suspended Remover

Category: Security  
Version: v1.0.80  
Visibility: Public  
Summary: High-precision account purification engine. Fleet-wide security infrastructure.

## Overview
High-precision account purification engine. Fleet-wide security infrastructure.

## Flowchart
[View flowchart image](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/suspended-remove-flowchart.png)

## Key Features
- Not documented yet.

## Permissions Used
- redis: Redis key-value storage (state tracking, caching, strike memory)

## Triggers and Activation
### Menu Actions
- GuardHub: Scan Modqueue for Suspended Users: Manually run the suspended user queue scan immediately (Location: subreddit)

### Custom Post Types and Entrypoints
- Features interactive custom post UI or Block views rendered natively on Reddit. (Entrypoint: src/main.ts)

## Settings Reference
Subreddit moderators configure the app in Mod Tools -> App Settings.

- enabled: Enable automated enforcement (boolean, default: true). Turn this off to pause all scan actions without uninstalling the app.
- recheckDays: Days between rechecks (number, default: 0). Default: 0 for legacy behavior and lowest rollout friction. Use 0 to allow back-to-back scheduled checks. Increase this if you want the app to wait full days between checks before final action.
- confirmChecks: Required verification checks (number, default: 1). Default: 1 for legacy behavior and lowest rollout friction. Increase this if you want the app to confirm the account is still inaccessible more than once before final action.
- duringWaitAction: What to do during the waiting window (select, default: filter_hide_waiting). Filter & Hide removes the item from public view and places it into the Needs Review / ModQueue queue during checks. Filter & Keep Public keeps the item visible to the public on the subreddit while keeping it in the Needs Review queue. Temporary Remove moves the item out of the review queue and into the removed queue while checks continue. Important: if the app approves a filtered or temporarily removed item later, Reddit may not run AutoModerator and other moderation checks on it again like a brand-new post or comment.
- addDuringWaitNote: Add mod note to item during waiting window (boolean, default: true). Adds the waiting-period note to the item when the waiting action is applied. Turn this off if you do not want a note on the item during the checking period.
- duringWaitReason: Waiting-period mod note text (string, default: [WAITING] Suspended account recheck pending.). This note is added to the item when the waiting-period action is applied. The default starts with [WAITING] so moderators can quickly see that this item is already being tracked and does not need manual action yet.
- approveRecoveredTempRemovals: Auto-approve if account recovers (hidden/temp-removed items) (boolean, default: true). If a later check shows the account is accessible again, the app will automatically approve items it hid via "Filter & Hide" or removed via "Temp Remove". This setting has no effect when "Filter & Keep Public" is selected (since those items were never hidden). Note: approving an item may not re-run AutoModerator or other moderation checks the same way a brand-new submission would.
- finalAction: Final action after threshold (select, default: remove). This is the preferred setting. Remove is recommended for most subreddits because it does not add spam signals to accounts that may be temporarily suspended by mistake. If both this and the deprecated setting below are configured, this setting is used first.
- markAsSpam: [Deprecated] Mark final removal as spam (boolean, default: false). This older setting is still shown for compatibility with existing installs. Use "Final action after threshold" above for new setup. If both are set, the new setting is used first.
- addFinalNote: Add mod note to item on final action (boolean, default: true). Adds the final-action note to the item when it is removed. Turn this off if you do not want a note on the item at removal time.
- finalReason: Final-action mod note text (string, default: Suspended account content removed — account inaccessible at time of removal.). This note is added to the item when the final action is applied.
- addUserNote: Add mod note to user on final action (boolean, default: true). Adds a note to the user's mod history when the final action fires. Only runs once, at final action time. Does not run during the waiting period.
- userNoteLabel: User note label (select, default: SPAM_WARNING). Badge shown on the mod note in the user's profile. None has the lowest impact on the account.
- userNoteText: User note text (string, default: Account is suspended or shadowbanned. Item automatically removed.). User note text
- legalDocs: Terms & Privacy (string, default: See help text for official documentation links.). legal.legal_docs_url

## Automation Capabilities
- Submits Automated Comments: No — Does not submit automated comments.
- Attaches Removal Notes: Yes — Attaches removal notes.
- Approves Content: Yes — Approves content.
- Removes or Filters Content: Yes — Removes or filters non-compliant submissions.
- Dispatches Modmail Alerts: No — Does not send modmail notifications.
- Updates User or Post Flair: No — Does not update flair.

## Data Storage
This app utilizes Reddit Redis storage for state management, caching, and rate limiting.

- Key-Value Strings (deduplication & cooldown markers)
- Hashes (structured records & alias indices)

## Setup and Usage
- Install: Add Suspended Remove to your subreddit through the Reddit App Directory.
- Configure Pipeline: Open Mod Tools > App Settings > Suspended Remove.
- Choose Waiting Mode: Select your preferred waiting-stage action (*Filter & Hide* recommended).
- Save: Background queue scanning activates immediately with zero manual maintenance.
- No more orphaned mod queue items. Clean, safe queue automation directly inside Reddit.*

## Troubleshooting
- Check app console logs via devvit logs <subreddit> for real-time diagnostic output.
- Ensure all required app settings and API keys are properly configured in Mod Tools.

## Version History
1.0.80 — 2026-08-16
- Fix: Removed duplicate manifest menu declaration in `devvit.json` to resolve double menu trigger in subreddit moderator tools.

1.0.79 — 2026-08-15
- Standard fleet synchronization and maintenance.

1.0.78 — 2026-08-15
- Standard fleet synchronization and maintenance.

## Links
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/suspended-remove/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/suspended-remove/PRIVACY.md)
- [GitHub Repository](https://github.com/grantdb/suspended-remove)
- [Support](https://www.reddit.com/r/grantdb)