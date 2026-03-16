# ChatApp – Real-Time Full-Stack Chat Application

A production-ready MERN stack chat app with Socket.io, Cloudinary, and Tailwind CSS.

## Tech Stack

| Layer      | Technology                              |
|------------|-----------------------------------------|
| Frontend   | React 18, Vite, Tailwind CSS, Socket.io-client |
| Backend    | Node.js, Express.js, Socket.io          |
| Database   | MongoDB Atlas (Mongoose ODM)            |
| Auth       | JWT + bcryptjs                          |
| Media      | Cloudinary                              |
| Deployment | Vercel (frontend + backend)             |

---

## Project Structure

```
chatapp/
├── client/           # React + Vite frontend
│   └── src/
│       ├── components/   # Sidebar, ChatContainer, RightSidebar
│       ├── pages/        # HomePage, LoginPage, ProfilePage
│       ├── context/      # AuthContext, ChatContext
│       └── lib/          # axios.js, utils.js
└── server/           # Node.js + Express backend
    ├── controllers/  # authController, messageController
    ├── models/       # User.js, Message.js
    ├── routes/       # authRoutes, messageRoutes
    ├── middleware/   # auth.js (protectRoute)
    └── lib/          # db.js, cloudinary.js, socket.js, utils.js
```

---

## Getting Started

### Prerequisites
- Node.js v18+
- MongoDB Atlas account
- Cloudinary account

### 1. Clone and setup

```bash
git clone <your-repo-url>
cd chatapp
```

### 2. Setup Server

```bash
cd server
npm install
cp .env.example .env
# Fill in your .env values (see below)
npm run dev
```

**Server `.env`:**
```
MONGODB_URI=mongodb+srv://<user>:<pass>@cluster.mongodb.net/chatapp
PORT=5000
JWT_SECRET=your_secret_key_here
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret
CLIENT_URL=http://localhost:5173
```

### 3. Setup Client

```bash
cd client
npm install
cp .env.example .env
# Edit .env if needed
npm run dev
```

**Client `.env`:**
```
VITE_API_URL=http://localhost:5000/api
VITE_SOCKET_URL=http://localhost:5000
```

### 4. Open the app
Visit [http://localhost:5173](http://localhost:5173)

---

## API Endpoints

### Auth (`/api/auth`)
| Method | Endpoint          | Auth | Description             |
|--------|-------------------|------|-------------------------|
| POST   | /signup           | No   | Register new user       |
| POST   | /login            | No   | Login existing user     |
| PUT    | /update-profile   | Yes  | Update name/bio/avatar  |
| GET    | /check-auth       | Yes  | Verify JWT token        |

### Messages (`/api/messages`)
| Method | Endpoint          | Auth | Description                      |
|--------|-------------------|------|----------------------------------|
| GET    | /users            | Yes  | Get users with unread counts     |
| GET    | /:userId          | Yes  | Get conversation messages        |
| POST   | /send/:userId     | Yes  | Send message (text/image)        |
| PUT    | /mark/:userId     | Yes  | Mark messages as seen            |

---

## Features
- ✅ Two-step signup flow
- ✅ JWT authentication with bcrypt password hashing
- ✅ Real-time messaging via Socket.io
- ✅ Image sharing via Cloudinary
- ✅ Online/offline status indicators
- ✅ Unread message badges
- ✅ Media gallery panel
- ✅ Profile editing with avatar upload
- ✅ Search/filter contacts
- ✅ Auto-scroll to latest message
- ✅ Responsive three-column layout
- ✅ Vercel deployment ready

---

## Deployment on Vercel

### Backend
1. Import `server/` folder as a new Vercel project
2. Set all environment variables in Vercel dashboard
3. Deploy

### Frontend
1. Import `client/` folder as a new Vercel project
2. Set `VITE_API_URL` and `VITE_SOCKET_URL` to your backend Vercel URL
3. Deploy

---

## Academic Details
- **Project:** ChatApp – Real-Time Full-Stack Chat Application
- **Stack:** MERN + Socket.io + Cloudinary
- **Academic Year:** 2024–2025
