# Privacy Policy for Flair Guard

Last updated: September 2026

This Privacy Policy describes how Flair Guard collects, uses, and protects information.

## Information Collection
Flair Guard operates within the Reddit Developer Platform (Devvit). It processes public submission data (post IDs, submission titles, and author usernames) to evaluate configured keyword rules and assign post flairs.

## Zero Personal Data Storage
Flair Guard does NOT collect, store, or sell personal identifying information (PII). Dedup tokens (`flairguard:processed:{postId}`) and temporary locks in Redis store only post IDs and boolean status indicators.

## Data Retention & Isolation
All deduplication markers in Redis are retained for post lifecycle management and automatically expire. All data remains strictly within subreddit-isolated Devvit storage.

## Contact
For questions, support, or privacy inquiries, contact the developer via r/grantdb.