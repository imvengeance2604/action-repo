# action-repo

Source repository that triggers GitHub webhook events.

This repository is configured to send webhook notifications when:
- Code is pushed (PUSH events)
- Pull requests are created or updated (PULL_REQUEST events)
- Branches are merged (MERGE events)

All webhook events are sent to the `webhook-repo` backend for storage and display.

## Setup

Clone this repository and configure it with webhook notifications:

```bash
git clone https://github.com/your-username/action-repo.git
cd action-repo
```

## Configure Webhook

The webhook is already configured in GitHub repository settings to POST to:
`https://webhook-repo-url.com/webhook`

To verify or reconfigure:
1. Go to Settings → Webhooks
2. Check that the webhook points to your webhook-repo endpoint
3. Ensure the content type is set to `application/json`

## Triggering Events

### PUSH Event
```bash
# Make changes and push
git add .
git commit -m "Your commit message"
git push origin main
```

### PULL_REQUEST Event
```bash
# Create a feature branch and open a pull request
git checkout -b feature-branch
# Make changes
git add .
git commit -m "Feature changes"
git push origin feature-branch
# Open PR on GitHub
```

### MERGE Event
When a pull request is merged via GitHub interface or:
```bash
# Merge locally and push
git merge feature-branch
git push origin main
```

## Monitoring

View all triggered events in the webhook-repo dashboard at:
`http://localhost:5000` (or your deployed URL)
