# bufu.ai

AI-Powered Virtual Try-On Platform

## Project Structure

```
bufu-ai/
├── frontend/         # Next.js + Tailwind CSS
├── backend/          # FastAPI (Python)
├── ai-inference/     # Placeholder for AI model integration
├── infra/            # Docker Compose, infrastructure configs
└── README.md         # Project overview and setup
```

## Quick Start (Local Dev)

1. **Clone the repo**
2. **Install Docker & Docker Compose**
3. **Run:**
   ```bash
   docker compose -f infra/docker-compose.yml up --build
   ```
4. **Frontend:** http://localhost:3000
start the frontend after running npm install
  cd frontend
   npm run dev
6. **Backend:** http://localhost:8000
start the backend after installing python and dependencies
   cd bufu-ai
      uvicorn backend.main:app --reload

---

## Directories

- `frontend/` – Next.js app (React, Tailwind CSS)
- `backend/` – FastAPI app (Python, REST API)
- `ai-inference/` – Placeholder for AI model code (e.g., VITON-HD)
- `infra/` – Docker Compose and infra configs

---

## Next Steps
- Connect frontend to backend
- Integrate AI model in `ai-inference/`
- Add authentication, billing, and more features 

## Hautech API Integration

### Environment Variables
Set the following in your backend environment (e.g., in a .env file or your deployment config):

```
HAUTECH_APP_ID=your_hautech_app_id
HAUTECH_APP_KEY_ID=your_hautech_app_key_id
HAUTECH_APP_KEY_SECRET=your_hautech_app_key_secret
```

### Try-On API Usage
- POST `/api/tryon` with form-data:
  - `apparel`: clothing image file
  - `model`: model image file
  - (optional) `sub`: user email/identifier
- Returns: `{ "result_url": "https://..." }` on success, or `{ "error": "..." }` on failure.

The backend securely handles Hautech API authentication and orchestration. # bufu.ai
