> **User Guide & Overview** | [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/modconnect)

# ModConnect

> **Connect the right people to the right community roles.**

ModConnect is a Reddit-native moderator recruiting, evaluation, and onboarding platform built with Devvit Web. It helps moderation teams publish structured application posts, privately review and score candidates, manage a clear recruiting pipeline, send respectful Modmail notifications, and guide accepted moderators through an onboarding checklist.

## At a Glance

- **Structured Role Creation**: Launch open roles from 3 built-in templates (Basic Moderator, Community Volunteer, Event Helper) with 6 question types, openings caps, and optional deadlines.
- **Interactive Application Posts**: Opening a role publishes an interactive post where community members apply, track their own status, and withdraw before a final decision.
- **Private Moderator Review & Pipeline**: Score candidates (1-5), record recommendations (accept, maybe, reject) and private notes, and move applicants through Submitted, In Review, Interview, Trial, Accepted, or Rejected.
- **Automated Modmail & Onboarding**: Receive archivable Modmail Inbox alerts on new applications, send polite decision notices without leaking private notes, and track 6 customizable onboarding tasks for accepted candidates.

## How It Works: The 5-Step Operational Pipeline

### 01 · Create & Open a Role

> **Publish a recruitment post with structured screening questions**
> - Open **ModConnect: Moderator Dashboard** or **ModConnect: Create Open Role** from your subreddit moderation menu.
> - Pick a default template or build custom questions (`shortText`, `longText`, `singleSelect`, `multiSelect`, `number`, `checkbox`).
> - Save as a Draft to iterate freely, or Open the role to automatically publish an interactive application post.

---

### 02 · Collect Community Applications

> **Validated, duplicate-free submissions scoped to your subreddit**
> - Community members open the recruitment post, review openings, eligibility, and deadline countdown, and submit their answers.
> - ModConnect blocks duplicate submissions, paused or closed roles, passed deadlines, and roles with zero remaining openings.
> - Moderators immediately receive an archivable Modmail Inbox notification with a link to review the candidate.

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
> - Accepting a candidate enforces the role's openings limit and dispatches a polite Modmail notice with a link to their onboarding checklist.
> - Rejecting a candidate sends a respectful, neutral Modmail notice with zero internal review details exposed.

---

### 05 · Track Onboarding & Recruiting Metrics

> **Guided checklists and simple pipeline visibility**
> - Accepted candidates automatically receive 6 default onboarding tasks that moderators can customize, reorder, add due dates to, or verify.
> - Both the accepted candidate and the moderation team can track completion percentage in real time.
> - Moderators view key Phase 1 metrics: total/open roles, applications by status, acceptance rate, average time to decision, active onboarding count, and onboarding completion rate.

## Moderator Workflow

1. Open **ModConnect: Moderator Dashboard** from the subreddit menu.
2. Click **Create Role**, choose one of the 3 templates, adjust openings/deadline/questions, and click **Create & Open Role**.
3. If a Reddit API or persistence interruption leaves a role in **Publish Failed**, ModConnect does not automatically retry or create duplicate posts. Review your subreddit feed and choose either **I found the post — link it** (paste the Reddit post URL or `t3_` ID to verify and open the role) or **No post was created — retry publication** (explicitly confirm no post exists before starting a new publish attempt).
4. Open the **Candidates** tab to filter by role or status, search by username, or sort by date, score, or status.
5. Click any candidate to inspect answers, submit a private 1-5 review, advance pipeline status, and record a final Accept or Reject decision.
6. Open the **Onboarding** tab to customize and track tasks for accepted candidates, and check **Metrics** or **Settings** to review stats and customize Modmail templates.

## Applicant Workflow

1. Open an active ModConnect recruitment post in the subreddit and click **Apply Now**.
2. Complete all required questions and submit the form.
3. Return to the post at any time to check your current pipeline stage or withdraw your application prior to a final decision.
4. If accepted, open your **Onboarding Checklist** directly from the post or acceptance Modmail and check off your assigned steps.

## Data Model

All records are strictly scoped per subreddit in Devvit Redis (`modconnect:v1:<subreddit>:*`):

- **Role**: `id`, `subredditName`, `title`, `description`, `openings`, `applicationDeadline`, `questions[]`, `status` (`draft | publishing | open | publish_failed | paused | closed`), `createdBy`, `createdAt`, `updatedAt`, `postId`, `postUrl`, and moderator-only `publication` attempt metadata.
- **Application**: `id`, `roleId`, `subredditName`, `applicantUsername`, `answers`, `status` (`submitted | inReview | interview | trial | accepted | rejected | withdrawn`), `submittedAt`, `updatedAt`, `decisionAt`, `decisionBy`, `decisionNote`.
- **Review**: `id`, `applicationId`, `reviewerUsername`, `score` (1-5), `recommendation` (`accept | maybe | reject`), `notes`, `createdAt`, `updatedAt`.
- **OnboardingTask**: `id`, `applicationId`, `title`, `description`, `order`, `required`, `status` (`pending | completed | skipped`), `completableBy`, `dueAt`, `completedAt`, `completedBy`.
- **AuditEvent**: `id`, `subredditName`, `type`, `actorUsername`, `targetType`, `targetId`, `metadata`, `createdAt`.

## Permissions Required

ModConnect requests least-privilege Devvit permissions:

- **Reddit API (`permissions.reddit: true`)**: Verify caller identity and moderator status, create interactive recruitment and dashboard posts, and send Modmail notifications.
- **Redis (`permissions.redis: true`)**: Persist subreddit-scoped roles, applications, reviews, onboarding tasks, notification templates, and audit events.
- **No external HTTP access**: All data stays inside Reddit's Devvit infrastructure.

## Local Development & Testing

```powershell
# From the repository root or apps/modconnect
npm run build --workspace=modconnect
npm run type-check --workspace=modconnect
npm run test --workspace=modconnect
```

To test interactively in a development subreddit:

```powershell
cd apps/modconnect
npx devvit playtest <your-dev-subreddit>
```

For quick local exploration, moderators can click **Load Demo Data** under the **Settings** tab in the Moderator Dashboard to populate sample roles, applications, a review, and an onboarding checklist (strictly opt-in and never run automatically).

## Known Phase 1 Limitations

- Accepted and rejected decisions are final in Phase 1 (reopening a decided application is not supported).
- Onboarding quizzes are acknowledgment-based checkboxes rather than graded multi-question exams.
- Single-subreddit scope only; cross-subreddit mod team recruiting is not included in Phase 1.
- No scheduled interview calendar, external webhook/Discord integrations, or AI screening.

## Planned Phase 2 Features

- Automatic account eligibility checks (minimum account age, subreddit karma, ban/mod-note flags).
- Graded onboarding quizzes and reusable subreddit-level onboarding templates.
- Configurable multi-moderator approval thresholds and structured interview rubrics.
- Optional exportable audit summaries and recruitment cycle archiving.

## Support

> **Official Support Community**: [https://www.reddit.com/r/grantdb](https://www.reddit.com/r/grantdb)

- **User Guide**: [https://www.reddit.com/r/grantdb/wiki/modconnect/](https://www.reddit.com/r/grantdb/wiki/modconnect/)
- **Technical Reference**: [https://www.reddit.com/r/grantdb/wiki/index/all-apps/modconnect/](https://www.reddit.com/r/grantdb/wiki/index/all-apps/modconnect/)

## Legal

- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/modconnect/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/modconnect/PRIVACY.md)

---

*ModConnect — Moderation Recruiting & Onboarding*

---
*Built for Reddit's moderator community.*
