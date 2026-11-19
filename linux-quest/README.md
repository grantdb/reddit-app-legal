> **User Guide & Overview** | [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/linux-quest)

# Linux Quest

> **Gamified Linux installation simulator and support-readiness trainer built natively inside Reddit.**

**Linux Quest** walks users through an interactive 14-stage Linux installation simulation covering hardware architecture, ISO selection, USB firmware setup, storage partitioning, graphics stacks, and post-install boot diagnostics. Whether the simulated install boots cleanly or hits a realistic configuration error, players finish with a structured Support Readiness Quiz and a copyable Markdown troubleshooting brief they can paste directly into real community support threads.

---

## At a Glance

- **Realistic Installation Simulation**: Covers x86_64 and ARM64 platforms, architecture-matched ISOs, GPT/MBR and UEFI/Legacy boot modes, disk partitioning, graphics driver stacks, and online updates.
- **Scenario-Aware Diagnostics**: Mismatched choices produce realistic boot outcomes (architecture mismatch, GRUB rescue, UEFI boot target missing, dual-boot mount error, display manager timeout, or proprietary GPU lockup).
- **Support Readiness Scoring**: Evaluates practical help-seeking habits (hardware context, verbatim logs, clear goals, prior attempts, and constructive tone) on a 0-100 scale with a per-post leaderboard.
- **Copyable Support Brief**: Generates a ready-to-paste Markdown troubleshooting template populated with system context and log-collection reminders.

---

## How It Works: The 4-Step Operational Pipeline

### 01 · Launch From a Subreddit Post
> **Moderators create an interactive Linux Quest post via the subreddit menu.**
> - Moderators select **Create Linux Quest Post** from the subreddit mod menu.
> - Community members see a zero-scroll inline preview card showing the current record holder and tap **Launch Simulator** to enter expanded mode.

---

### 02 · Configure Hardware, Media, and Storage
> **Players walk through a guided Linux installation wizard.**
> - Select target hardware (AMD Ryzen, Intel Core, Raspberry Pi 5, or Hybrid Mobile) and an architecture-appropriate ISO (Arch Linux, Debian 12, or Fedora 41).
> - Configure USB flashing tools, partition scheme (GPT or MBR), firmware boot mode (UEFI, Legacy BIOS, or Compatible), disk layout, desktop environment, graphics stack, and online updates.

---

### 03 · Boot Validation and Anomaly Review
> **The simulator evaluates the full configuration end-to-end.**
> - Runs distro-specific deployment and kernel boot logs matching the selected hardware device path and packages.
> - Displays either a clean desktop boot or the exact failure caused by configuration conflicts, along with plain-language explanations and `journalctl` / `dmesg` recovery commands.

---

### 04 · Support Readiness Quiz and Shareable Brief
> **Players practice writing an actionable community support post.**
> - Complete a 6-question scenario-aware quiz scored out of 100 and persisted to the post leaderboard via Redis.
> - Copy the generated Markdown **Support Readiness Brief** to use when asking for real-world help in the subreddit.

---

## Quick Setup

1. **Install**: Add **Linux Quest** to your subreddit from the Reddit App Directory.
2. **Create a Post**: Open your subreddit's moderator menu and click **Create Linux Quest Post**.
3. **Share with Members**: Pin the post or link to it in your subreddit sidebar, rules, or help wiki so new users can practice before opening a support thread.

---

## Support

> **Need help, found a bug, or have a feature request?**
> Post in the official support community at [https://www.reddit.com/r/grantdb](https://www.reddit.com/r/grantdb) with the app name (`linux-quest`), what you expected, what happened, and any screenshots or error text.

- **Full User Guide**: [https://www.reddit.com/r/grantdb/wiki/linux-quest/](https://www.reddit.com/r/grantdb/wiki/linux-quest/)
- **Technical Reference & Settings Spec**: [https://www.reddit.com/r/grantdb/wiki/index/all-apps/linux-quest/](https://www.reddit.com/r/grantdb/wiki/index/all-apps/linux-quest/)

---

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/linux-quest/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/linux-quest/PRIVACY.md)

---
*Built for fun on Reddit*
