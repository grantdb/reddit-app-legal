> **User Guide & Overview** | [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/linux-quest)

# Linux Quest

> **Gamified Linux installation simulator and support-readiness trainer built natively inside Reddit.**

**Linux Quest** walks users through an interactive 14-stage Linux installation simulation covering hardware architecture, ISO selection, USB firmware setup, storage partitioning, graphics stacks, and post-install boot diagnostics. Whether the simulated install boots cleanly or hits a realistic configuration error, players finish with a structured Support Readiness Quiz and a copyable Markdown troubleshooting brief they can paste directly into real community support threads.

---

## At a Glance

- **Realistic Everyday Systems**: Practice installing Linux on common hardware — Older Business Laptop (Core i5 / 8GB / 256GB SSD), Everyday Desktop PC (Core i5 / 16GB / 512GB NVMe), Midrange Gaming PC (Ryzen 5 / GTX 1660), and Aging Pre-2012 Laptop (Core i3 / 4GB / Legacy BIOS).
- **Popular Distros & Installer Defaults**: Choose Linux Mint 22 (`ext4`), Pop!_OS 24.04 (`ext4` + `FAT32` Recovery), Fedora 41 (`Btrfs`), or EndeavourOS (`ext4`/`Btrfs`) with contextual summary hints across every step.
- **Real-Life Flashing & Account Setup**: Pick your target USB stick, formatter (`Rufus`, `Ventoy`, `BalenaEtcher`), USB filesystem (`FAT32`/`exFAT`/`NTFS`), GPT/MBR scheme, firmware boot mode, distro-matched Desktop Environment, graphics drivers, and user login (username + password).
- **Support Readiness Scoring & Brief**: Evaluates practical help-seeking habits on a 0-100 scale with a per-post Redis leaderboard and a copyable Markdown troubleshooting brief.

---

## How It Works: The 4-Step Operational Pipeline

### 01 · Launch From a Subreddit Post
> **Moderators create an interactive Linux Quest post via the subreddit menu.**
> - Moderators select **Create Linux Quest Post** from the subreddit mod menu.
> - Community members see a zero-scroll inline preview card showing the current record holder and tap **Launch Simulator** to enter expanded mode.

---

### 02 · Configure Hardware, USB Media, and Storage
> **Players walk through a guided, real-world Linux installation wizard.**
> - Pick an everyday PC or laptop and a popular distro (Linux Mint 22, Pop!_OS 24.04, Fedora 41, or EndeavourOS).
> - Follow contextual summary hints while selecting the USB drive, flashing tool (`Rufus`, `Ventoy`, `BalenaEtcher`), USB filesystem (`FAT32`, `exFAT`, `NTFS`), GPT/MBR scheme, firmware boot mode, distro-matched storage (`ext4`/`Btrfs`/`FAT32`), user account (username + password), Desktop Environment, and graphics drivers.

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
