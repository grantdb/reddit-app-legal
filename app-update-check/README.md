# App Update Checker

The App Update Checker is a specialized administrative tool designed to help subreddit moderators monitor updates for all custom logic and applications installed on their community. It provides proactive notifications, ensuring your moderation team is always using the most current and secure versions of your favorite tools.

## Features

- **Automated Discovery**: Scans the Subreddit ModLog upon activation to identify and register existing applications for monitoring.
- **Intelligent Update Detection**: Performs background polling of the Reddit Developer Portal to instantly recognize new patches or feature releases.
- **Proactive Notifications**: Dispatches a detailed ModMail alert when an update is detected, including direct links to the update configuration.
- **Manual Management**: Offers precise control via Subreddit Settings and Mod Menu actions to manually track or untrack specific items as needed.

## Technical Configuration

The tool utilizes Reddit's native scheduling and state management to ensure reliable monitoring without manual intervention:

| Component | Functionality |
|---------|-------------|
| **Backend Polling** | Secure synchronization with the Developer Portal. |
| **State Storage** | Tracks version history and registered app slugs. |
| **Notification Engine** | Automated ModMail dispatching for real-time updates. |

---
*Built for the Reddit community.*
