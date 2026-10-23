# 📸 Instagram Clone - Full-Stack Social Network (MERN)

[![React](https://img.shields.io/badge/React-18-61DAFB?style=flat-square&logo=react&logoColor=black)](https://react.dev)
[![Node.js](https://img.shields.io/badge/Node.js-18+-339933?style=flat-square&logo=node.js&logoColor=white)](https://nodejs.org)
[![Express](https://img.shields.io/badge/Express-4.18-000000?style=flat-square&logo=express&logoColor=white)](https://expressjs.com)
[![MongoDB](https://img.shields.io/badge/MongoDB-Mongoose-47A248?style=flat-square&logo=mongodb&logoColor=white)](https://mongodb.com)
[![MUI](https://img.shields.io/badge/Material--UI-v5-007FFF?style=flat-square&logo=mui&logoColor=white)](https://mui.com)
[![JWT](https://img.shields.io/badge/JWT-Auth-black?style=flat-square&logo=json-web-tokens&logoColor=white)](https://jwt.io)

A responsive, feature-rich social media application inspired by Instagram. Built with the **MERN stack (MongoDB, Express, React, Node.js)**, **Material-UI (MUI)**, and **JWT authentication**, featuring post creation, likes, comments, user following, and user profile feeds.

---

## 🌟 Key Features

- 🔐 **Authentication & Security:** Secure user signup and login with hashed passwords via `bcryptjs` and session tokens with `jsonwebtoken`.
- 🖼️ **Post Feed & Media Sharing:** Upload posts with image URLs, captions, and real-time like/unlike counters.
- 💬 **Interactive Comments:** Commenting threads on posts with nested author details.
- 👥 **Follower System:** Follow and unfollow users with dynamic feed updates reflecting followed accounts.
- 📱 **Modern UI/UX:** Styled using Material-UI (MUI) components, Emotion, and Sass for a responsive, mobile-friendly interface.
- 🛡️ **Protected REST APIs:** Server-side route middleware verifying authorization tokens on private endpoints.

---

## 🏗️ Architecture

```
project-root/
│
├── client/                 # React Frontend
│   ├── public/
│   └── src/
│       ├── components/     # Reusable UI widgets (Posts, Feed, Navbar, Stories)
│       ├── pages/          # Home, Login, Register, Profile pages
│       └── App.js          # App routing and theme providers
│
└── server/                 # Express REST API Backend
    ├── models/             # Mongoose schemas (User, Post)
    ├── routes/             # Authentication, Post, and User routes
    └── index.js            # Express server initialization & MongoDB connection
```

---

## ⚡ Quick Start

### Prerequisites

- Node.js (v18+)
- MongoDB (Local instance or MongoDB Atlas connection URI)

---

### 1. Backend Setup

```bash
cd server
npm install
```

Create a `.env` file in `server/`:

```env
PORT=8800
MONGO_URL=mongodb://localhost:27017/socialmedia
JWT_SECRET=your_super_secret_jwt_key
```

Run the backend server:

```bash
npm start
# Runs on http://localhost:8800
```

---

### 2. Frontend Setup

In a new terminal window:

```bash
cd client
npm install
npm start
# Runs on http://localhost:3000
```

---

## 📡 REST API Summary

### Authentication

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `POST` | `/api/auth/register` | Register a new user |
| `POST` | `/api/auth/login` | Log in and receive JWT token |

### Posts

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `POST` | `/api/posts` | Create a new post |
| `GET` | `/api/posts/:id` | Fetch specific post details |
| `PUT` | `/api/posts/:id/like` | Like or unlike a post |
| `GET` | `/api/posts/timeline/all` | Fetch user feed timeline |

### Users

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `GET` | `/api/users/:id` | Fetch user profile info |
| `PUT` | `/api/users/:id/follow` | Follow a user |
| `PUT` | `/api/users/:id/unfollow` | Unfollow a user |
