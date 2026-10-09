# EV Charging App

Backend and frontend skeleton for finding electric-vehicle charging stations and tracking their availability.

## Structure

- `backend/` — FastAPI service backed by MongoDB. Station data comes from the TomTom and Open Charge Map APIs; Celery workers (Redis broker) run the periodic real-time and batch refresh tasks.
- `frontend/` — React app (Create React App) with Leaflet and Axios. It is still the starter scaffold.

## Running the backend

```bash
cd backend
python -m venv venv && source venv/bin/activate
pip install -r requirements.txt
cp .env.example .env   # fill in your own TomTom keys and a JWT secret
uvicorn app.main:app --reload
```

MongoDB and Redis must be running locally (see `.env.example` for the default URLs). The Celery worker entry point is `celery_worker.py`.

## Running the frontend

```bash
cd frontend
npm install
npm start
```
