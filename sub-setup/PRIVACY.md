# Privacy Policy for Sub Setup (sub-setup)

## What This App Reads

Sub Setup reads subreddit configuration data available through its
moderator-scoped Reddit API access:

- Subreddit settings (description, sidebar, icon, banner, content settings, community type)
- AutoModerator configuration (config/automoderator wiki page)
- Post and user flair templates
- Community rules and removal reasons
- Wiki pages (index page only, to check if the wiki is enabled)
- Moderator team membership and permission levels

## What This App Stores

The most recent audit report is stored in Reddit's app storage (Redis) for the
subreddit where the app is installed, using the key prefix `sub-setup:`.

Stored data includes the complete audit report JSON (settings summaries and
check results) and the timestamp of the most recent audit.

Data is associated with the subreddit, not with individual moderators.

## What This App Does Not Collect

- Post or comment content, or submission history
- Individual user profiles, account history, or private messages
- Internal modmail conversations
- Detailed ban-evasion signals or account-level risk scores
- Personal moderator information beyond team membership counts and permission levels

## Where Data Is Sent

The audit report is delivered to the subreddit's Modmail (Mod Discussions).
No data is sent to any external server or third-party service.

## Data Retention

Audit data in Redis is overwritten each time a new audit is run. Reddit's
platform manages data lifecycle after app uninstallation according to their
terms of service.

## Questions

Contact the app developer through the subreddit where this app is listed.
