# ApplyPilot Frontend

React + Vite frontend for ApplyPilot — Your Personal Career Command Center.

## Requirements
- Node.js 18.18+ (Node.js 20 LTS recommended)
- The ApplyPilot Express backend running at `http://localhost:5000`
- A configured MongoDB Atlas URI in `../backend/.env`

## Setup (Windows / VS Code)
From the project root, install all dependencies:

```powershell
npm install
npm --prefix backend install
npm --prefix frontend install
```

Create `frontend/.env` from the example:

```powershell
Copy-Item frontend/.env.example frontend/.env
```

Set `VITE_API_URL=http://localhost:5000/api` in `frontend/.env` if needed. This is a public API base URL, not a place for database credentials. Never put `MONGODB_URI` in frontend environment variables.

Start the frontend from the project root:

```powershell
npm --prefix frontend run dev
```

Or run the root development command to start both backend and frontend:

```powershell
npm run dev
```

Open http://localhost:5173.

## Frontend commands
- `npm run dev` — Vite development server
- `npm run build` — production build into `dist/`
- `npm run preview` — preview the production build

## Notes
- All application data and analytics are loaded from the backend API; the frontend does not use mock records.
- Company search and status filtering are sent to the backend as query parameters.
- Application status transitions and delete restrictions are also enforced by the backend.
- CSV export exports the currently loaded/filtered list.
- If the dashboard cannot connect, verify that the backend is running and that `VITE_API_URL` is correct.
