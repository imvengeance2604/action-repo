# action-repo

This repository is the **source** repository that triggers GitHub webhook events
(Push, Pull Request, Merge) which are captured by the
[webhook-repo](https://github.com/<you>/webhook-repo) receiver.

---

## How it works

1. You push commits, open pull requests, or merge branches **here**.
2. GitHub fires a webhook to the `webhook-repo` endpoint.
3. The endpoint stores the event in MongoDB.
4. The UI (served by `webhook-repo`) polls MongoDB every **15 seconds** and
   displays the latest activity.

---

## Registered Webhook

| Setting       | Value                                      |
|---------------|--------------------------------------------|
| Payload URL   | `https://<your-ngrok-or-server>/webhook`   |
| Content type  | `application/json`                         |
| Events        | Pushes, Pull requests                      |
