# Privacy Policy for AI Checker

Effective Date: April 28, 2026

## 1. Information Collection
The `ai-checker` Devvit application is a moderator tool designed to analyze Reddit posts for AI-generated content.

- **Data we access:** When a moderator manually triggers a scan, the app accesses the content of the selected Reddit post (text and/or image URLs).
- **Data we collect:** The app does NOT collect, store, or transmit any personally identifiable information (PII) beyond what is necessary to perform the scan and post the result comment.
- **Data Storage:** We use Reddit's `kvStore` or installation settings only to store configuration (API keys, templates). We do not store a persistent database of scanned content.

## 2. Third-Party Data Processing
To provide AI detection results, the app transmits post content (text or image URLs) to the following third-party AI detection providers, depending on the moderator's active configuration:
- **GPTZero** (gptzero.me)
- **Sightengine** (sightengine.com)
- **Hive AI** (thehive.ai)

These providers receive only the content required for analysis. Please refer to their respective privacy policies for how they handle submitted data.

## 3. Storage and Security
All processing is performed within the secure Reddit Devvit sandbox environment. Sensitive API keys are stored using Reddit's secure secret management system.

## 4. Consent
By installing and using `ai-checker` in your subreddit, you consent to the app performing manual content analysis and posting automated results as described.

## 5. Contact
If you have any questions or concerns regarding this privacy policy, please contact the app developer via Reddit.
