# AI Car Comparison Assistant

## What
Full-stack website that compares two cars using a rule-based AI scoring module with optional LLM explanations.

## How to run
1. Backend:
   - `cd backend`
   - `python -m venv venv`
   - `source venv/bin/activate` (mac/linux)
   - `./venv/Scripts/Activate.ps1` (windows PowerShell)
   - `pip install -r requirements.txt`
   - `cp .env.example .env`
   - `uvicorn app.main:app --reload --port 8000`

2. Frontend:
   - `cd frontend`
   - `npm install`
   - `npm run dev`
   - open `http://localhost:5173`

## Notes
- Database: `backend/cars.db` will be created automatically and persists.
- To use OpenAI LLM explanations, fill `.env` with `USE_OPENAI=true` and `OPENAI_API_KEY=...`

## Optional improvements & submission tips (for PLP)
- Replace cars.csv with a larger dataset (Kaggle car datasets). Keep data cleaning script if needed.
- Add unit tests for `ai_module.py` scoring.
- Add Dockerfiles to containerize backend + frontend.
- Add CI (GitHub Actions) to run tests and linting.
- Add sample recordings/screenshots of your demo.
- Write a short report describing architecture, dataset, model, limitations, and ethics (bias in pricing, fairness).

## Quick troubleshooting
- If CORS errors appear: ensure backend is running and CORS in `main.py` allows your frontend origin (for production change `allow_origins`).
- If database not populated: ensure `backend/app/data/cars.csv` exists and contains rows before first run.
- If `npm install` fails: make sure Node.js and npm are installed (Node >= 16 recommended).