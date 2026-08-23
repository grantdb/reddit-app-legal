> 📖 **User Guide & Overview** | ⚙️ [View Deep Technical Reference & Settings Spec](https://www.reddit.com/r/grantdb/wiki/index/all-apps/link-guard)

# GuardHub: Link Guard

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Hardened-red?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Security-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Content_Policy-8A2BE2?style=for-the-badge)

> **Unmask shorteners, detect malicious redirects, and block link threats automatically.**

Link Guard protects your subreddit from phishing links, disguised shorteners, affiliate spam, and malicious redirect chains. Combining multi-provider threat intelligence, DNS security lookups, and automated redirect expansion, it audits community links without manual testing.

---

## At a Glance

- **Unmask shorteners**: Automatically trace redirect chains (`bit.ly`, `t.co`, `tinyurl`) to their final destinations.
- **Block malicious links**: Check links against open threat feeds (URLhaus) and DNS-over-HTTPS security lookups.
- **Filter affiliate spam**: Detect and remove unauthorized referral codes, tracking query strings, and custom patterns.
- **Spot obfuscated links**: Catch disguised link text (e.g. `example[dot]com`) and Punycode homograph attacks.
- **Test in Audit Mode**: Preview link matches safely in the background before applying live moderation actions.

---

## The Old Way vs. The Link Guard Way

| Traditional Workflow | With Link Guard |
| :--- | :--- |
| Clicking suspicious shortened URLs to see where they lead | **Automated redirect tracing** expanding hidden destinations safely |
| Manually checking domain blacklists for phishing links | **Multi-source threat lookups** via DNS security and threat feeds |
| Spammers bypassing filters with `example(dot)com` syntax | **Obfuscation decoding** normalizing masked links automatically |
| Testing complex link rules directly on live community posts | **Dry-Run Audit Mode** logging simulated rule matches quietly |
| Mod team unsure which link triggered a post removal | **Detailed match logs** displaying the full expanded URL and matched rule |

---

## Built for Comprehensive Link Security

- **Redirect Expansion Engine**: Automatically resolves HTTP redirect hops to reveal destination URLs hidden behind link shorteners.
- **Multi-Source Threat Intelligence**: Cross-references links with open threat feeds (URLhaus) and DNS security services (Cloudflare 1.1.1.2 & Quad9).
- **VirusTotal Integration**: Optionally connect your VirusTotal API key for deep malware and phishing analysis against custom detection thresholds.
- **Heuristics & Homograph Shield**: Detects raw IP hosts, high-risk TLDs, Punycode homograph spoofing, and embedded basic auth credentials.
- **Flexible Action Modes**: Configure rules to silently remove, filter to mod queue, report for review, or log exclusively in Audit Mode.
- **Dedicated Management Center**: Access a private dashboard from Subreddit Mod Tools to inspect link metrics, test URLs, and configure scanning tiers.

---

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/link-guard-flowchart.png)

### Your Four-Step Workflow

1. **Extract**: Link Guard extracts raw URLs, Markdown hyperlink targets, and obfuscated link patterns from new submissions and comments.
2. **Resolve**: Shortened URLs are traced through HTTP redirect chains to identify final canonical destinations.
3. **Scan**: Target links are evaluated against active security rules, threat feeds, DNS lookups, and custom pattern filters.
4. **Enforce**: When a violation is detected, Link Guard executes the configured action (`filter`, `remove`, `spam`, or `report`).

---

## Quick Setup

1. **Install**: Add **Link Guard** to your subreddit through the Reddit App Directory.
2. **Configure**: Open **GuardHub: LinkGuard Dashboard** from Subreddit Mod Tools.
3. **Select Rules**: Enable URL shortener resolution, threat feed matching, and custom pattern filters in Audit Mode.
4. **Enforce**: Once satisfied with audit logs, switch your rules to Live mode.

*No dangerous manual URL clicking. Comprehensive automated link security in your native dashboard.*

---

## Advanced Capabilities

Link Guard is engineered for fast URL analysis and safe redirect resolution across high-volume communities.

- **HTTP Redirect Chain Resolver**: Follows HTTP 301/302 redirect locations up to configurable hop limits to uncover destination hosts.
- **DNS-over-HTTPS Security Lookups**: Queries Cloudflare Security DNS (`security.cloudflare-dns.com`) and Quad9 (`dns.quad9.net`) without API keys.
- **Punycode & Homograph Detector**: Identifies internationalized domain names (IDNs) and Cyrillic/Greek character replacements mimicking popular domains.
- **Pattern & Query String Matcher**: Supports regex targeting specific URL paths, query parameters (`utm_source`, `ref`), or specific URL keywords.

---

## Designed to Assist Moderators

Link Guard provides automated link inspection and threat feed scanning to assist community safety. Threat lookups and heuristic indicators serve as assistive signals rather than definitive proof of malicious intent—human moderators retain full authority to approve filtered links in mod queue, whitelist trusted domains, and adjust security sensitivity at any time.

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
