# PERN Auth Starter

Minimal full-stack authentication starter built with PostgreSQL, Express, React, and Node.

**Stack:** PERN + Drizzle ORM + JWT + TypeScript

---

## Tech Stack

**Backend**
- Node.js + Express
- PostgreSQL
- Drizzle ORM
- JWT + bcrypt
- CORS

**Frontend**
- React (Vite)
- TypeScript
- Context API
- Axios
- Tailwind CSS

---

## Project Structure

```
backend/
  src/
    db/
    modules/auth/
    middlewares/
    utils/

frontend/
  src/
    api/
    auth/
    lib/
```

---

## Setup

### 1. Clone

```bash
https://github.com/NishulDhakar/pern-auth-starter.git
cd pern-auth-starter
```

### 2. Backend Setup

```bash
cd backend
npm install
```

Create `.env`:

```env
DATABASE_URL=postgresql://postgres:password@localhost:5432/authdb
JWT_SECRET=your-secret-key
PORT=3001
```

Run migrations:

```bash
npm run db:generate
npm run db:migrate
```

Start server:

```bash
npm run dev
```

**Backend runs on:** `http://localhost:3001`

### 3. Frontend Setup

```bash
cd frontend
npm install
npm run dev
```

**Frontend runs on:** `http://localhost:5173`

---

## API Endpoints

### Register
```http
POST /auth/register
Content-Type: application/json

{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "password123"
}
```

### Login
```http
POST /auth/login
Content-Type: application/json

{
  "email": "john@example.com",
  "password": "password123"
}
```

**Response:**
```json
{
  "user": { "id": 1, "name": "John Doe", "email": "john@example.com" },
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}
```

Token is stored in `localStorage` and automatically attached to requests via Axios interceptors.

---

## Auth Flow

```
Register → Login → JWT Token → Protected Routes → Database Access
```

- Passwords hashed with bcrypt
- JWT tokens for authentication
- `requireAuth` middleware protects backend routes
- `ProtectedRoute` component guards frontend routes

---

## Commands

**Backend:**
```bash
npm run dev          # Start dev server
npm run db:generate  # Generate migrations
npm run db:migrate   # Run migrations
```

**Frontend:**
```bash
npm run dev    # Start dev server
npm run build  # Production build
```

---

## Features

✅ User registration and login  
✅ Password hashing (bcrypt)  
✅ JWT authentication  
✅ Protected API routes  
✅ Protected frontend routes  
✅ Clean, minimal architecture  

---

## What's Next?

Extend this starter with:
- Refresh tokens
- Logout endpoint
- Role-based access control
- Password reset flow
- Docker setup
- Production deployment

---

**License:** MIT
