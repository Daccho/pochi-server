# Pochi Server 🧸🧠

The unified backend server for Pochi (WearOS & Web).
Built with Go, deployed to Google Cloud Run.

## Features
- **Dual Endpoints:**
  - `POST /api/chat` (Web format)
  - `POST /api/v1/chat` (WearOS legacy format)
- **Context Aware:** Loads `SOUL.md` and other context files.
- **Provider:** Anthropic Claude API.

## Local Development

1. Set API Key:
   ```bash
   echo "ANTHROPIC_API_KEY=sk-ant-..." > .env
   ```

2. Run:
   ```bash
   go run main.go
   ```

## Deployment (Cloud Run)

```bash
gcloud run deploy pochi-server \
  --source . \
  --region asia-northeast1 \
  --allow-unauthenticated \
  --set-env-vars ANTHROPIC_API_KEY="YOUR_KEY"
```
