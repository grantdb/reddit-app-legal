# Privacy Policy for Mod Dispatch

Last updated: November 9, 2026

## Information Collection
This application operates on the Reddit platform via the Devvit runtime and coordinates moderation queue reviews among authorized subreddit moderators. It does not collect, sell, or transmit any personally identifiable information (PII) or user tracking profiles.

## Data Usage
- Coordination Data: Claim states, timestamps, shared moderator notes, suggestions, and handoffs are stored securely within Reddit's platform-managed Redis storage with configurable retention periods (default 30 days).
- Privacy Safeguards: Moderator notes, claim states, and audit trails are strictly restricted to authenticated subreddit moderators and are never exposed to regular community members.
- Zero External Transmission: Unless the subreddit moderators explicitly configure optional Discord or Slack webhook notification URLs, no data is sent outside Reddit. When webhooks are enabled, notifications include only non-PII operational titles, item IDs, and moderator notes.

## Third-Party Services
External communications are limited to user-configured Discord or Slack webhook endpoints for real-time team alerts.

## Contact
If you have questions regarding this privacy policy, please contact the developer via r/grantdb.

