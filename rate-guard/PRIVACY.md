# Privacy Policy for RateGuard

Last Updated: July 2026

RateGuard is built with privacy-first data retention principles.

1. **Information Processed**: RateGuard processes post submission timestamps (`Date.now()`), post IDs (`t3_...`), and usernames.
2. **Zero Content Storage**: RateGuard DOES NOT store post body text, titles, image URLs, or author PII.
3. **Data Retention**: Post timestamps older than 30 days are automatically pruned from Redis.
4. **Data Isolation**: All user history is stored in subreddit-isolated Devvit Redis storage.
