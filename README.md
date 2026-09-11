# AI CRM Dashboard

An AI-powered CRM (Customer Relationship Management) dashboard for managing contacts, leads, notes, and tasks — with AI features powered by Google Gemini.
<img width="1919" height="947" alt="Screenshot 2026-09-11 123910" src="https://github.com/user-attachments/assets/6131586a-7db8-4da8-aef6-6ebe3be3f16b" />

## Tech Stack

**Backend**
- Node.js + Express
- MongoDB with Mongoose
- JWT authentication
- Google Gemini (`@google/genai`) for AI features

**Frontend**
- React 19 + Vite
- Tailwind CSS
- Redux Toolkit
- React Router
- Recharts (analytics charts)
- @dnd-kit (drag-and-drop, e.g. Kanban-style boards)

## Project Structure

```
AI_CRM_Dashboard/
├── backend/
│   ├── config/          # Database connection
│   ├── controllers/     # Route logic (auth, contacts, leads, notes, tasks, analytics, AI)
│   ├── middleware/       # Auth + error handling
│   ├── models/           # Mongoose schemas
│   └── server.js
└── frontend/
    └── AICRMDashboard/
        ├── src/
        └── vite.config.js
```

## Getting Started

### Prerequisites
- Node.js (v18+ recommended)
- npm
- A MongoDB instance (local or Atlas)
- A Google Gemini API key

### 1. Clone the repo

```bash
git clone <your-repo-url>
cd AI_CRM_Dashboard
```

### 2. Backend setup

```bash
cd backend
npm install
```

Create a `.env` file in `backend/` (see `.env.example` if present) with:

```
PORT=
NODE_ENV=
CLIENT_URL=
MONGO_URI=
JWT_SECRET=
JWT_EXPIRES_IN=
GEMINI_API_KEY=
GEMINI_MODEL=
```

Run the backend:

```bash
npm run dev     # development, with nodemon
npm start       # production
npm run seed    # seed the database (if applicable)
```

### 3. Frontend setup

```bash
cd frontend/AICRMDashboard
npm install
```

Create a `.env` file with:

```
VITE_API_URL=http://localhost:8000/api
```

Run the frontend:

```bash
npm run dev       # start dev server
npm run build     # production build
npm run preview   # preview production build
```

## Environment Variables

| Variable | Location | Description |
|---|---|---|
| `PORT` | backend | Port the API server runs on |
| `NODE_ENV` | backend | `development` or `production` |
| `CLIENT_URL` | backend | Frontend URL, used for CORS |
| `MONGO_URI` | backend | MongoDB connection string |
| `JWT_SECRET` | backend | Secret used to sign JWTs |
| `JWT_EXPIRES_IN` | backend | JWT token expiry (e.g. `7d`) |
| `GEMINI_API_KEY` | backend | Google Gemini API key |
| `GEMINI_MODEL` | backend | Gemini model name to use |
| `VITE_API_URL` | frontend | Base URL the frontend calls for the API |

> **Never commit real `.env` files.** Use the variable names above (or an `.env.example`) to document what's needed, and keep actual secrets local or in your deployment platform's secret manager.

## Features

- User authentication (JWT-based)
- Contact management
- Lead tracking
- Notes and tasks per contact/lead
- Analytics dashboard
- AI-assisted features via Google Gemini
