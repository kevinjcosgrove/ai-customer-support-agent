# Security & Public-Repo Checklist

Before publishing any project material publicly, verify that the repository contains **none** of the following:

- API keys
- Access tokens
- Authentication headers
- `.env` files
- Webhook secrets
- Private URLs
- Retell production agent IDs or knowledge-base IDs
- Customer phone numbers, email addresses, or addresses
- Private conversation transcripts
- Internal client notes
- Pricing or policies that were shared privately rather than published publicly
- Proprietary source documents
- Credentials or screenshots showing account information
- Real test-customer personal information

## Client Anonymization

Use a generic client name such as **Home Services Company** unless you have explicit permission to publish the real company name and internal project material.

Public website facts may be publicly accessible, but a consolidated internal knowledge base, prompt architecture, missing-information notes, testing records, and workflow design may still be inappropriate to publish without permission.

## Before Every Push

Run:

```bash
git status
git diff --cached
```

Review every staged file before committing.

Do not commit `.env` or credential files, even temporarily. Removing them in a later commit does not automatically remove them from Git history.
