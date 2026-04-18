# AI-Powered E-commerce Automation Backend

This project is a modular FastAPI backend scaffold for an AI-powered e-commerce automation system.

## Features

- FastAPI application with a clean modular structure
- Separate folders for `agents`, `pipeline`, and `api` routes
- Environment-based configuration using `pydantic-settings`
- OpenAI API key support via `.env`
- Basic test endpoint for quick verification

## Project Structure

```text
.
├── app
│   ├── agents
│   ├── api
│   │   └── routes
│   ├── core
│   ├── pipeline
│   ├── schemas
│   ├── services
│   └── main.py
├── .env.example
├── .gitignore
├── README.md
└── requirements.txt
```

## Setup

1. Create a virtual environment and activate it.
2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Copy the environment file and add your API key:

```bash
cp .env.example .env
```

4. Run the server:

```bash
uvicorn app.main:app --reload
```

## Test Endpoint

Once the server is running, open:

- `GET /`
- `GET /api/v1/health`

## Notes

- The `agents` package is where AI task agents should live.
- The `pipeline` package is intended for workflow orchestration and automation logic.
- The `services` package includes shared integrations such as the OpenAI client setup.

## Vercel Deployment

This repository is easiest to deploy to Vercel as two projects:

1. Backend project
   - Import the repository into Vercel
   - Set the Root Directory to the repository root
   - Add environment variables from `.env.example`
   - Set `CORS_ORIGINS` to include your deployed frontend URL

2. Frontend project
   - Import the same repository again
   - Set the Root Directory to `frontend`
   - Add `VITE_API_BASE_URL` using `frontend/.env.example`
   - Point it to your deployed backend URL
