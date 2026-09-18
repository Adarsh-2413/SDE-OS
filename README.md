# 🚀 SDE OS

> **The ultimate all-in-one workspace for Software Development Engineers.**
> Track your Data Structures and Algorithms (DSA) progress, manage your job applications, and streamline your interview preparation in one modern, full-stack application.

![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)
![React](https://img.shields.io/badge/React-18-blue)
![Node.js](https://img.shields.io/badge/Node.js-18+-green)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15-blue)

---

## ✨ Features

- 🔐 **Secure Authentication**: JWT-based login, registration, and session management.
- 📊 **DSA Progress Tracker**: Seamlessly track problems solved, accuracy, and spaced repetition schedules.
- 💼 **Job Pipeline Management**: Keep tabs on job applications, interview stages, and offers.
- ⚙️ **Automated Background Jobs**: Uses Redis and BullMQ for heavy lifting and scheduled tasks.
- 🎨 **Modern Interface**: Clean, responsive, and beautiful UI built with React, Vite, and TailwindCSS.
- ☁️ **Media Management**: Integrated with Cloudinary for seamless image and file uploads.

---

## 🏗️ Architecture & Data Flow

```mermaid
graph TD
    Client[React Frontend] -->|REST API / HTTP| API[Express Backend]
    API -->|Read/Write| DB[(PostgreSQL)]
    API -->|Cache / Queues| Cache[(Redis)]
    Cache -->|Process Jobs| Worker[BullMQ Worker]
```

---

## 🛠️ Tech Stack

### Frontend
- **Framework**: React (Bootstrapped with Vite)
- **Styling**: TailwindCSS
- **State Management & Fetching**: React Query / Axios

### Backend
- **Runtime**: Node.js
- **Framework**: Express.js
- **ORM**: Prisma
- **Background Jobs**: BullMQ

### Infrastructure
- **Database**: PostgreSQL (via Docker)
- **Cache / Message Broker**: Redis (via Docker)
- **Containerization**: Docker & Docker Compose

---

## 🚀 Getting Started

Follow these steps to set up the project locally on your machine.

### Prerequisites
Make sure you have the following installed:
- [Node.js](https://nodejs.org/) (v18 or higher)
- [Docker & Docker Desktop](https://www.docker.com/products/docker-desktop)
- [Git](https://git-scm.com/)

### 1. Clone the repository
```bash
git clone https://github.com/Adarsh-2413/SDE-OS.git
cd SDE-OS
```

### 2. Environment Variables
Create a `.env` file in the `backend` directory based on the provided example. You will need your own Cloudinary keys if you plan to test image uploads.
```bash
PORT=5000
DATABASE_URL="postgresql://admin:password123@localhost:5432/sde_os_db?schema=public"
ACCESS_TOKEN_SECRET="your_super_secret_access_token"
REFRESH_TOKEN_SECRET="your_super_secret_refresh_token"
CLIENT_URL="http://localhost:5173"
REDIS_URL="redis://localhost:6379"
CLOUDINARY_CLOUD_NAME="your_cloud_name"
CLOUDINARY_API_KEY="your_api_key"
CLOUDINARY_API_SECRET="your_api_secret"
```

### 3. Install Dependencies
Install packages for both the frontend and the backend.
```bash
# Install backend dependencies
cd backend
npm install

# Install frontend dependencies
cd ../frontend
npm install
cd ..
```

### 4. Start Infrastructure (Databases)
Start the PostgreSQL and Redis containers in the background using Docker.
```bash
docker-compose up -d
```

### 5. Run the Application
You can now start both the backend and frontend development servers.

**Terminal 1 (Backend):**
```bash
cd backend
npm run dev
```

**Terminal 2 (Frontend):**
```bash
cd frontend
npm run dev
```

Your frontend should now be running at `http://localhost:5173` and your backend API at `http://localhost:5000`.

---

## 🤝 Contributing

Contributions, issues, and feature requests are always welcome!
Feel free to check the [issues page](https://github.com/Adarsh-2413/SDE-OS/issues) if you want to contribute.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📝 License

This project is open-source and available under the [MIT License](LICENSE).