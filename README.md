# GET FIT FITNESS STUDIO
Premium Gym Management Platform

Luxury fitness studio management system with real-time member tracking, CRM, payments, and analytics.

## Features
- **Stunning Luxury UI**: Pure CSS animated background with red ambient lighting, floating bubbles, premium dark theme.
- **Member Check-In**: Fast member lookup by ID or name, instant check-in/out with live status.
- **Admin Dashboard**: Live occupancy (Socket.IO), key metrics, real-time updates.
- **Full Member CRM**: Add, edit, suspend, delete, photo upload (base64), detailed profiles.
- **Payment Management**: Record payments, track pending/partial/paid, due members.
- **Reports & Analytics**: Attendance, revenue, growth, pending fees, peak hours with beautiful animated charts (no external chart libs).
- **Real-time**: Socket.IO powers live floor occupancy and data sync.
- **Premium Interactions**: GSAP counters, Framer Motion transitions/hovers, smooth everything.

## Tech Stack
- Frontend: Vite + React 18, React Router, Zustand, Axios, Framer Motion, GSAP, Socket.IO Client, Tailwind CSS, Lucide Icons, date-fns
- Backend: Node.js + Express, Socket.IO, CORS, in-memory + JSON file persistence

## Project Structure
```
get-fit-studio/
├── frontend/          # React + Vite app
├── backend/           # Express + Socket.IO API
├── render.yaml        # Render.com Blueprint for full deploy
└── README.md
```

## Quick Start (local, when you have Node.js installed)

### 1. Frontend
```bash
cd get-fit-studio/frontend
npm install
npm run dev
```
Runs on http://localhost:5173 by default.

### 2. Backend (separate terminal)
```bash
cd get-fit-studio/backend
npm install
npm start
```
Runs on http://localhost:3001 . Socket.IO attached.

## Deployment

### Render.com (recommended - both frontend and backend)

1. Push this repo to GitHub.
2. On Render.com: New > Blueprint > select this repo.
3. It will create:
   - Backend Web Service (Node + Socket.IO)
   - Frontend Static Site
4. After first deploy, set env vars:
   - Backend: `CORS_ORIGIN=https://<frontend-onrender-url>`
   - Frontend: `VITE_BACKEND_URL=https://<backend-onrender-url>`
5. Redeploy both.

See render.yaml for details.

## Default Admin Credentials
- Admin ID: `admin123`
- Password: `admin123`

Use the **Admin Access** button on home to login.

## Notes
- All data is persisted to JSON files in `backend/data/` (members.json, payments.json, attendance.json).
- Photos are stored as base64 strings in member records (demo only; fine for dozens of members).
- Seed data is created on first backend start (5 sample members).
- Real-time occupancy updates across clients via Socket.IO.
- For production: Consider adding a real database (e.g. Postgres on Render) and proper auth.

## Key Design Tokens
See `frontend/src/styles/colors.js` and global CSS variables.

Built to the exact luxury gym management specification.

## License
Internal / Demo