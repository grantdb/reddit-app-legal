# Privacy Policy for AutoMod Easy

Effective Date: April 17, 2026

AutoMod Easy (the "App") is committed to protecting the privacy of moderators and community members.

### 1. Information Collection
The App does not collect or store personal identifying information (PII) on external servers. 

### 2. Data Storage and Use
- **Wiki Configurations**: The App reads and writes to your subreddit's `config/automod` wiki page using the Reddit API.
- **Backups**: The App stores temporary snapshots of your configuration in Reddit's internal Redis storage. These snapshots are used solely for the "Self-Healing" rollback feature and are localized to your subreddit's installation.
- **Authentication**: The App uses Reddit's native OAuth system provided via the Devvit platform. We never see or store your Reddit password.

### 3. Third-Party Sharing
No data collected or processed by the App is shared with, sold to, or accessible by any third parties. All data remains within the Reddit ecosystem.

### 4. Security
The App uses the secure Devvit runtime environment provided by Reddit. Modifying AutoMod configurations is restricted to users with the appropriate moderator permissions.

### 5. Contact
For questions regarding this privacy policy, please contact the developer via Reddit.
