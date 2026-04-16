# Privacy Policy for Distro Feed

Effective Date: April 15, 2026

## 1. Information Collection
The `distro-feed` Devvit application is designed to automatically post Linux and BSD distribution release updates to Reddit.

- **Data we access:** The bot fetches publicly available information from **Google News RSS** (news.google.com) based on specific search queries related to Linux distribution releases.
- **Data we collect:** The bot does NOT collect, store, or transmit any personally identifiable information (PII), user data, account details, or browsing history of Reddit users. 
- **Data Storage:** We use Reddit's `kvStore` to store the unique identifiers (GUIDs) of the last processed release announcements to prevent duplicate posts. This data is internal to the application and not shared.

## 2. Storage and Security
The bot does not maintain an external database. All data processing is performed within the secure Reddit Devvit sandbox environment using ephemeral memory and Reddit's built-in KV store.

## 3. Third-Party Access
We do not share, sell, or distribute any information to third parties. Network requests are strictly limited to fetching the search-grounded RSS feed from Google News.

## 4. Consent
By installing and using `distro-feed` in your subreddit, you consent to the bot performing its automated polling and posting duties as described.

## 5. Contact
If you have any questions or concerns regarding this privacy policy, please contact the bot developer via Reddit.
