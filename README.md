# SDE OS

SDE OS is a full-stack web application designed to help developers track their DSA progress, manage job applications, and streamline their interview preparation.

### Tech Stack

**Client:** React, Vite, TailwindCSS (for styling)
**Server:** Node.js, Express
**Database & Caching:** PostgreSQL (via Prisma), Redis
**Queue:** BullMQ (for background jobs)

### Running Locally

You'll need Docker installed to spin up the database and Redis cache.

1. Clone the project and install dependencies:
   ```bash
   npm install
   cd frontend && npm install
   cd ../backend && npm install
   ```

2. Start the databases using Docker:
   ```bash
   docker-compose up -d
   ```

3. Run the backend and frontend dev servers (in separate terminal tabs):
   ```bash
   # Tab 1: Backend
   cd backend
   npm run dev

   # Tab 2: Frontend
   cd frontend
   npm run dev
   ```

### Features
- JWT-based authentication
- DSA problem tracking and progress management
- Automated background tasks using Redis & BullMQ
- Clean, modern UI built with React

---

Feel free to open issues or submit pull requests if you want to contribute!