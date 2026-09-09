> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/link-guard)

# GuardHub: Link Guard 🛡️

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Hardened-red?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Security-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Content_Policy-8A2BE2?style=for-the-badge)

> **Unmask shorteners, decode obfuscated links, and enforce link policies automatically.**

Link Guard protects your subreddit from disguised link shorteners, phishing attempts, affiliate tracking spam, and obfuscated domain tricks (`example[dot]com`). Operating entirely within Reddit's sandboxed environment with zero external API dependencies, it audits community submissions and comments with zero-latency local evaluation.

---

## At a Glance

- **Block disguised shorteners**: Automatically catch 30+ known URL shortener domains (`bit.ly`, `tinyurl.com`, `t.co`, `cutt.ly`) before users leave Reddit.
- **Spot obfuscated links**: Decode disguised syntax such as `domain[dot]com` or `domain (dot) com` and Punycode homograph spoofing attacks (`xn--`).
- **Filter affiliate & tracking spam**: Detect and remove unauthorized referral links, tracking query parameters, and custom keyword patterns.
- **Curated threat directory**: Check incoming links against a built-in directory of high-risk TLDs, raw IP hostnames, and known threat indicators.
- **Test in Audit Mode**: Preview link matches safely in the background before applying live moderation actions.

---

## The Old Way vs. The Link Guard Way

| Traditional Workflow | With Link Guard |
| :--- | :--- |
| Clicking suspicious shortened URLs to see where they lead | **Automated shortener identification** flagging risky redirect domains |
| Spammers bypassing filters with `example[dot]com` syntax | **Obfuscation decoding** normalizing masked links automatically |
| Phishing bots hiding behind Punycode homographs (`xn--`) | **Homograph & IP Shield** detecting spoofed character sets and raw IPs |
| Testing complex link rules directly on live community posts | **Dry-Run Audit Mode** logging simulated rule matches quietly |
| Mod team unsure which link triggered a post removal | **Detailed match logs** displaying the detected URL and matched rule |

---

## Built for Comprehensive Link Security

- **Shortener Shield**: Instantly detects links originating from link shorteners and redirection relays without leaking community URLs to external servers.
- **Obfuscation Decoder**: Automatically extracts hidden URLs written in evasion syntax like `site[dot]xyz` or `paypal (dot) com`.
- **Heuristics & Homograph Shield**: Detects raw IP hosts, high-risk TLDs, Punycode homograph spoofing, embedded credentials, and excessive subdomain nesting.
- **Flexible Action Modes**: Configure rules to silently remove, filter to mod queue, report for review, or log exclusively in Audit Mode.
- **Dedicated Management Center**: Access a private dashboard from Subreddit Mod Tools to inspect link metrics, test URLs, and configure scanning rules.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/link-guard-flowchart.png)

### Your Four-Step Workflow

1. **Extract**: Link Guard extracts raw URLs, Markdown hyperlink targets, and obfuscated link patterns from new submissions and comments.
2. **Decode**: Normalizes obfuscated syntax, flags known shortener domains, and inspects Punycode hostnames.
3. **Evaluate**: Evaluates links against the curated threat directory, heuristic risk indicators, and custom pattern filters.
4. **Enforce**: When a violation is detected, Link Guard executes the configured action (`filter`, `remove`, `spam`, or `report`).

---

## Quick Setup

1. **Install**: Add **Link Guard** to your subreddit through the Reddit App Directory.
2. **Configure**: Open **GuardHub: LinkGuard Dashboard** from Subreddit Mod Tools.
3. **Select Rules**: Enable URL shortener filtering, threat directory matching, and custom pattern filters in Audit Mode.
4. **Enforce**: Once satisfied with audit logs, switch your rules to Live mode.

*No dangerous manual URL clicking. Comprehensive automated link security in your native dashboard.*

---

## Advanced Capabilities

Link Guard is engineered for fast URL analysis across high-volume communities.

- **Instant Local Analysis**: Zero outbound network requests—100% compliant with Reddit's data privacy and security sandbox.
- **Punycode & Homograph Detector**: Identifies internationalized domain names (IDNs) and character spoofing attacks mimicking popular domains.
- **Pattern & Keyword Matcher**: Supports keyword and substring pattern matching targeting specific URL paths, query parameters (`utm_source`, `ref`), or domain keywords.
- **Mod Exemption Controls**: Configurable exemption rules allow moderators to post administrative or verification links without triggering automated filters.

---

## Designed to Assist Moderators

Link Guard provides automated link inspection and threat directory matching to assist community safety. Heuristic indicators serve as assistive signals rather than definitive proof of malicious intent—human moderators retain full authority to approve filtered links in mod queue, whitelist trusted domains, and adjust security sensitivity at any time.

---

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

---

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/link-guard/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/link-guard/PRIVACY.md)

---
*Built for Reddit's moderator community. Part of the GuardHub family.*
