> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/gimmecode-guard)

# GuardHub: GimmeCode Guard 🛡️

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Hardened-red?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Automation-8A2BE2?style=for-the-badge)

> **Filter low-effort code begging and keep developer discussions focused and high-value.**

GimmeCode Guard protects programming and tech subreddits from repetitive "give me code" demands, homework begging, and low-effort copy-paste requests. Using pattern scoring and code block awareness, it nudges users toward constructive inquiry while preserving meaningful technical discussions.

---

## At a Glance

- **Filter low-effort code requests**: Identify phrases like "code please", "send source", or "do this for me".
- **Code block awareness**: Automatically ignores comments that include actual code samples or snippets.
- **Configurable action thresholds**: Choose between gentle warning replies, mod queue reports, or removals.
- **90-day strike memory**: Track repeat offenders across the subreddit with persistent strike history.
- **Unified moderator controls**: Access audit logs, database maintenance, and configuration guides from the **GimmeCode Guard** menu popout.
- **Direct comment inspections**: Check any user's strike history directly from comment menus using **GimmeCode: Check User History**.

---

## The Old Way vs. The GimmeCode Guard Way

| Traditional Workflow | With GimmeCode Guard |
| :--- | :--- |
| Comment sections flooded with "plz send code" begging | **Automated phrase detection** filtering low-effort requests instantly |
| Manually writing repetitive warnings explaining rule requirements | **Automated educational replies** guiding users to ask better questions |
| Accidental filter flags on legitimate code explanations | **Context-aware parsing** exempting Markdown and indented code blocks |
| Forgetting which users repeatedly beg for homework solutions | **90-day rolling strike memory** tracking repeat offender infractions |
| Searching mod logs to review an author's history | **Native comment action menu** inspecting user strikes with one tap |

---

## Built for High-Quality Developer Communities

- **Smart Request Detection**: Evaluates multi-token phrases and variations commonly used in low-effort source code requests.
- **Context-Aware Immunity**: Intelligently exempts comments containing valid Markdown code blocks (` ``` ` or 4-space indentation).
- **Graduated Moderation Actions**: Configure independent score thresholds for automated warning replies, mod reports, or direct removals.
- **Long-Term Strike Memory**: Tracks author violation strikes in Redis over 90-day rolling windows to identify habitual freeloaders.
- **Unified Subreddit Menu Popout**: Select **GimmeCode Guard** from the subreddit overflow menu (`...`) to access:
  - **Audit Logs**: Generate and deliver consolidated audit reports directly to team Modmail on demand.
  - **Reset Database**: Purge cached violation tallies and start fresh.
  - **Settings Guide**: Review current threshold rules and detection sensitivity.
- **Comment Menu Inspection**: Open any comment menu (`...`) and click **GimmeCode: Check User History** to view the author's community strike records instantly.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/gimmecode-guard-flowchart.png)

### Your Four-Step Workflow

1. **Submit**: A user submits a comment in the subreddit.
2. **Analyze**: GimmeCode Guard evaluates the text for code-begging patterns while checking for valid code blocks.
3. **Score**: If low-effort request markers exceed threshold scores, the comment is flagged and logged to Redis.
4. **Action**: The configured action (automated educational warning, mod queue report, or removal) executes immediately.

---

## Quick Setup

1. **Install**: Add **GimmeCode Guard** to your subreddit through the Reddit App Directory.
2. **Configure**: Open **Mod Tools > App Settings > GimmeCode Guard**.
3. **Set Thresholds**: Configure your desired scores for warning replies, reports, or removals.
4. **Save**: Automated protection activates immediately across all new comment submissions.

*No complex regex configuration required. Clean technical discussions for your developer community.*

---

## Advanced Capabilities

GimmeCode Guard is engineered for fast comment parsing and accurate intent detection across active programming communities.

- **Phrase Scoring Matrix**: Evaluates multi-token phrase dictionaries with weighted keyword matching.
- **Markdown AST Code Block Filter**: Detects fenced code blocks, inline snippets, and indented text to protect genuine technical help.
- **Rolling 90-Day Redis Hash**: Persists user strike tallies and violation timestamps with automatic TTL decay.
- **Native Context Menu Extension**: Registers custom moderator menu actions on comments for rapid historical lookups.

---

## Designed to Assist Moderators

GimmeCode Guard detects and scores low-effort code requests to assist in maintaining technical discussion standards. Scoring serves as an assistive filter—human moderators maintain full authority to review flagged comments, approve exceptions, and adjust detection sensitivity at any time.

---

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

---

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/gimmecode-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/gimmecode-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
