> **User Guide & Overview** | [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/modconnect)

# ModConnect

> **Connect the right people to the right community roles.**

ModConnect is a Reddit-native moderator recruiting, evaluation, and onboarding platform built with Devvit Web. It helps moderation teams publish structured application posts with automated account eligibility checks, privately review and score candidates, manage a clear recruiting pipeline with reversible decisions and audit exports, send respectful Modmail notifications, and guide accepted moderators through an onboarding checklist.

## At a Glance

- **Structured Roles & Automated Eligibility**: Launch open roles from 3 built-in templates (Basic Moderator, Community Volunteer, Event Helper) with 6 question types, openings caps, optional deadlines, and automatic checks for account age, karma, verified email, and subreddit ban status.
- **Interactive Recruitment Posts**: Opening a role publishes a subreddit-branded recruitment post where community members verify eligibility, apply, track their own status, and withdraw before a final decision.
- **Private Moderator Review & Audit Trail**: Score candidates (1-5), record recommendations and private notes, advance applicants through the pipeline, safely reopen rejected applications or revoke acceptances when plans change, and export audit logs as CSV or Markdown.
- **Archivable Modmail & Onboarding**: Receive archivable Modmail Inbox alerts on new applications, send polite decision notices without leaking private notes, and track 6 customizable onboarding tasks for accepted candidates.

## How It Works: The 5-Step Operational Pipeline

### 01 · Create & Open a Role

> **Publish a recruitment post with structured screening questions and eligibility rules**
> - Open **ModConnect: Moderator Dashboard** or **ModConnect: Create Open Role** from your subreddit moderation menu.
> - Pick a default template or build custom questions (`shortText`, `longText`, `singleSelect`, `multiSelect`, `number`, `checkbox`) and optional account eligibility rules (minimum account age, karma, verified email, or ban-list exclusion).
> - Save as a Draft to iterate freely, or Open the role to publish an interactive recruitment post with safe publication recovery if Reddit's API is interrupted.

---

### 02 · Screen & Collect Community Applications

> **Validated, duplicate-free submissions scoped to your subreddit**
> - Community members open the recruitment post, see live openings, deadline countdown, and their account eligibility status, and submit their answers.
> - ModConnect enforces eligibility requirements server-side and blocks duplicate submissions, paused or closed roles, passed deadlines, and roles with zero remaining openings.
> - Moderators immediately receive an archivable Modmail Inbox notification with a direct link to review the candidate.

---

### 03 · Review, Score & Discuss Privately

> **Collaborative moderator evaluation with strict privacy isolation**
> - Each moderator can submit and update one review per candidate with a 1-5 score, recommendation (`accept`, `maybe`, `reject`), and private notes.
> - ModConnect aggregates average scores and recommendation counts without ever auto-accepting or auto-rejecting candidates.
> - Applicants can never see other applicants, reviewer identities, scores, notes, or audit history.

---

### 04 · Advance Pipeline & Notify Candidates

> **Controlled status transitions with full audit logging**
> - Moderators move candidates through `submitted -> inReview -> interview -> trial -> accepted | rejected`.
> - Accepting a candidate enforces the role's openings limit and dispatches a polite Modmail notice with a link to their onboarding checklist; rejecting sends a respectful notice with zero internal details exposed.
> - Moderators can reopen a rejected application back to In Review or remove an accepted candidate if needed, with every change recorded in the exportable audit log.

---

### 05 · Track Onboarding & Recruiting Metrics

> **Guided checklists and clear pipeline visibility**
> - Accepted candidates automatically receive 6 default onboarding tasks that moderators can customize, reorder, assign due dates to, or verify.
> - Both the accepted candidate and the moderation team can track completion progress in real time.
> - Moderators view recruiting metrics (total/open roles, applications by status, acceptance rate, average time to decision, and onboarding completion rate) and export audit history as CSV or Markdown.

## Quick Setup

1. **Install**: Add **ModConnect** to your subreddit from the Reddit App Directory.
2. **Open Dashboard**: Launch **ModConnect: Moderator Dashboard** from your subreddit moderation menu.
3. **Publish First Role**: Click **Create Role**, choose a template, configure any eligibility rules and questions, and click **Create & Open Role**.

---

## Support

> **Community Support & Feature Requests**
> For questions, troubleshooting, or bug reports, join the official community:
> **[https://www.reddit.com/r/grantdb](https://www.reddit.com/r/grantdb)**

- **User Guide**: [https://www.reddit.com/r/grantdb/wiki/modconnect/](https://www.reddit.com/r/grantdb/wiki/modconnect/)
- **Technical Reference**: [https://www.reddit.com/r/grantdb/wiki/index/all-apps/modconnect/](https://www.reddit.com/r/grantdb/wiki/index/all-apps/modconnect/)

---

## Legal

- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/modconnect/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/modconnect/PRIVACY.md)

---
*Built for Reddit's moderator community.*
