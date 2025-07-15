# Copilot Instructions for Mergington High School Activities API

## Overview
This project is a simple FastAPI application for managing extracurricular activities at Mergington High School. It allows students to view available activities and sign up for them. The backend is implemented in Python using FastAPI, and a static frontend is served from the `src/static/` directory.

## Key Components
- `src/app.py`: Main FastAPI application. Defines API endpoints and in-memory data model.
- `src/static/`: Contains static frontend files (`index.html`, `app.js`, `styles.css`).
- `src/README.md`: Project-specific documentation, including API usage and setup instructions.

## Data Model
- Activities are stored in-memory as a dictionary in `app.py`.
- Each activity has a name, description, schedule, max participants, and a list of participant emails.

## API Endpoints
- `GET /activities`: Returns all activities and their details.
- `POST /activities/{activity_name}/signup?email=...`: Registers a student for an activity (no duplicate check by default).

## Developer Workflows
- **Install dependencies:** `pip install fastapi uvicorn`
- **Run the app:** `python src/app.py` (or use `uvicorn src.app:app --reload` for auto-reload)
- **Access docs:** [http://localhost:8000/docs](http://localhost:8000/docs)
- **Frontend:** Open `src/static/index.html` directly or via the root endpoint `/`.

## Project Conventions
- No persistent storage: all data is lost on restart.
- No authentication or authorization.
- No duplicate registration check: students can register multiple times for the same activity (see `signup_for_activity`).
- Static files are served from `/static`.

## Example Patterns
- To add a new activity, update the `activities` dictionary in `app.py`.
- To prevent duplicate signups, add a check before appending to `participants`.

## Integration Points
- No external APIs or databases are used.
- All logic is contained within `src/app.py`.

---

For more details, see `src/README.md` and inline comments in `src/app.py`.
