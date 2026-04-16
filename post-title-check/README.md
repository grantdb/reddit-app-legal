# Post Title Check

A powerful Reddit automation tool that enforces title standards, ensuring your subreddit remains organized and high-quality. This app automatically validates new submissions against your custom rules and provides clear, helpful feedback to users.

## Features

- **Word Count Enforcement**: Set minimum length requirements to ensure post titles are descriptive.
- **Banned Phrases**: Instantly block specific keywords or prohibited phrases (case-insensitive).
- **Mandatory Tagging**: Require users to include bracketed categories (e.g., [News], [Update], [Help]).
- **Character Validation**: Enforce ASCII/English-only titles to maintain subreddit readability.
- **Intelligent Feedback**: Automatically posts a stickied removal comment with the exact reason for the violation.
- **Resubmission Assistance**: Provides users with a copy-paste ready version of their title to simplify the correction process.

## Configuration

Moderators can fine-tune the app behavior directly from the Mod Tools menu:

| Setting | Description |
|---------|-------------|
| **Minimum Word Count** | Define the minimum words required (Default: 3). |
| **Banned Phrases** | A comma-separated list of blocked terms. |
| **Require Brackets** | Toggle mandatory [...] style tagging. |
| **English / ASCII Only** | Restrict titles to standard English characters. |
| **Custom Message** | Customize the preamble for all removal notifications. |

## How It Works

1. **Scan**: Every new post is analyzed the moment it is submitted.
2. **Validate**: The title is checked against your specific subreddit configuration.
3. **Act**: If a violation is found, the post is removed instantly.
4. **Notify**: The author receives a stickied comment and a private message explaining how to fix their title and resubmit.

---
*Built on Reddit's Developer Platform.*
