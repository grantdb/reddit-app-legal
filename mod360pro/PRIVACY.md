# Privacy Policy for Mod360 Pro

Last updated: September 22, 2026

This Privacy Policy describes how Mod360 Pro handles information.

## Information Collection
Mod360 Pro operates entirely within Reddit's Devvit platform ecosystem and only inspects public submissions, comments, and public metadata within subreddits where it is installed. The application does not collect, sell, or persist Personally Identifiable Information (PII).

## Data Usage & Storage
1. **Moderator Status & Karma Caching**: Temporarily cached in isolated Reddit Redis storage to prevent redundant API lookups.
2. **Frequency Data**: Rate-limiting timestamps and duplicate content hashes are stored in volatile Redis sets with automated time-to-live (TTL) expiration.
3. **Audit Records**: Zero-PII action logs are maintained in Reddit Redis solely for subreddit moderator inspection.

## Third-Party Services
When AI inspection is enabled, post text is evaluated via Google Cloud Generative Language API strictly for spam detection according to Reddit developer policies.

## Contact
For support or questions regarding Mod360 Pro, contact u/grantdb or visit r/grantdb.
