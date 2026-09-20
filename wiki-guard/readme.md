> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/wiki-guard)

# Wiki-Guard 🛡️

> **Mobile-first, full-fidelity subreddit wiki management and editing for Reddit moderators.**

Subreddit wiki pages are essential for community guidelines, FAQs, wikis, and resource indexes, but managing them on mobile devices or inside Reddit mobile apps has historically been difficult or impossible. **Wiki-Guard** provides a dedicated, mobile-optimized moderator portal for browsing, creating, editing, previewing, and configuring subreddit wiki pages directly from inline custom posts and mobile browsers.

### ⚡ Key Highlights
- **Mobile-First Markdown Editor**: Clean, distraction-free editing with full support for line breaks, indentation, and standard Reddit Markdown syntax.
- **Instant Client-Side Preview**: Real-time sanitized Markdown preview with XSS protection and safe link validation.
- **Dual V1/V2 Wiki Compatibility**: Intelligently resolves between modern Wiki V2 and legacy V1 systems with fallback and manual mode overrides.
- **Strict Server-Side Authorization**: Every write and configuration operation is verified server-side against live moderator rosters.
- **Focused Scope**: Dedicated solely to subreddit wiki pages. Intentionally contains zero AutoModerator tools, post queues, or unrelated mod functions.

---

## Core Features
- **Zero-Friction Page Navigation**: Quickly filter and locate nested wiki pages (e.g. `rules`, `faq`, `resources/setup`).
- **Preserved Source of Truth**: The raw Markdown text is preserved verbatim without destructive HTML conversion or stripping.
- **Version Awareness**: Automatically checks whether your subreddit supports Reddit's Wiki V2 platform, while supporting legacy V1 subreddits seamlessly.
- **Granular Page Settings**: Manage whether pages are listed in the subreddit index and enforce subreddit or moderator-only permission levels.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/wiki-guard-flowchart.png)

```
[Moderator Menu] ──> [Portal Custom Post] ──> [Server Auth Guard]
                                                      │
                       ┌──────────────────────────────┴──────────────────────────────┐
                       ▼                                                             ▼
             [Wiki Page Browser]                                            [Markdown Editor]
          • Search / Filter Slugs                                      • Raw Textarea Source
          • V1 / V2 Version Tags                                       • Dirty State Detection
          • Metadata Inspection                                        • Sanitized Live Preview
                       │                                                             │
                       └──────────────────────► [Reddit API] ◄───────────────────────┘
                                          • createWikiPage
                                          • updateWikiPage
                                          • updateWikiPageSettings
```

### The 4-Step Lifecycle
1. **Launch Portal**: The moderator triggers the `Wiki-Guard: Subreddit Wiki Editor` menu item from their subreddit, opening the dedicated custom post portal.
2. **Server-Side Verification**: Wiki-Guard validates that the active user is an authorized moderator of the subreddit before displaying controls or accepting API requests.
3. **Browse & Edit**: The moderator navigates existing wiki pages or initiates a new page, drafting content in a mobile-friendly editor with instant sanitized previewing.
4. **Direct Reddit Commit**: Changes are committed directly to Reddit's official Wiki API with explicit revision reasons and version targeting.

---

## Quick Setup (60-Second Onboarding)

1. **Install App**: Install Wiki-Guard to your subreddit from the Reddit Developer portal.
2. **Open Portal**: From your subreddit menu, select **Wiki-Guard: Subreddit Wiki Editor**.
3. **Browse Pages**: View your community's active wiki pages, search existing paths, or tap **Create New Page**.
4. **Draft & Save**: Edit Markdown content, verify using the **Preview** tab, and commit your changes instantly.

---

## The Old Way vs. The Wiki-Guard Way

| Feature | The Old Way | The Wiki-Guard Way |
| :--- | :--- | :--- |
| **Mobile Wiki Access** | Desktop mode zoom gymnastics in mobile browsers | Responsive, finger-friendly mobile webview |
| **Markdown Editing** | Unforgiving text inputs prone to accidental back-nav | Dirty-state tracking and unsaved change confirmation |
| **Live Preview** | Save and refresh live page on Reddit to check formatting | Instant sanitized tabbed preview before saving |
| **Wiki System Support** | Manual guesswork between V1 and V2 wikis | Built-in detection and version-targeted requests |

---

## Designed to Assist Moderators / Privacy & Ethics

* **Moderator Authority**: Wiki-Guard empowers human moderators. All edits, saves, and settings changes are performed explicitly by authenticated moderators.
* **Strict Scope Isolation**: Wiki-Guard is a focused wiki editing tool. It does not read, edit, validate, deploy, or manage AutoModerator.
* **Zero PII & No HTTP Egress**: Wiki-Guard operates with zero external network access, storing no personal user data or tracking credentials.

---

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

---

## Legal

- [Terms of Service](TERMS.md)
- [Privacy Policy](PRIVACY.md)
