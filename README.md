# 💬 Chatty — Real-Time Chat Application

A full-stack real-time chat application built with React, Node.js, Socket.IO, and MongoDB.

![Chatty App](https://img.shields.io/badge/Status-Live-brightgreen) ![React](https://img.shields.io/badge/React-19-blue) ![Socket.IO](https://img.shields.io/badge/Socket.IO-4.8-black)

---

## 🚀 Live Demo

🌐 [https://chat-app-client-ten-liard.vercel.app](https://chat-app-client-ten-liard.vercel.app)

---

## ✨ Features

- 🔐 **Authentication** — Signup, Login, Logout with JWT cookies
- 💬 **Real-time messaging** — Instant messages using Socket.IO
- 🖼️ **Image sharing** — Send images in chat
- 👤 **Profile management** — Update profile picture
- 🟢 **Online status** — See who's online in real time
- 🎨 **32+ Themes** — Switch between themes powered by DaisyUI
- 📱 **Responsive design** — Works on mobile and desktop

---

## 🛠️ Tech Stack

### Frontend
| Tech | Version | Purpose |
|------|---------|---------|
| React | 19 | UI Framework |
| Vite | 7 | Build Tool |
| Tailwind CSS | 4 | Styling |
| DaisyUI | 5 | UI Components |
| Zustand | 5 | State Management |
| Socket.IO Client | 4.8 | Real-time communication |
| Axios | 1.x | HTTP requests |
| React Router DOM | 7 | Routing |
| Lucide React | 0.5 | Icons |

### Backend
| Tech | Purpose |
|------|---------|
| Node.js + Express | REST API Server |
| MongoDB + Mongoose | Database |
| Socket.IO | WebSocket Server |
| JWT | Authentication |
| Cloudinary | Image Storage |
| bcrypt | Password Hashing |

---

## 📁 Project Structure

```
chat-app-client/
├── public/
├── src/
│   ├── components/
│   │   ├── ChatContainer.jsx      # Main chat window
│   │   ├── ChatHeader.jsx         # Chat top bar with user info
│   │   ├── MessageInput.jsx       # Text & image input
│   │   ├── Navbar.jsx             # Top navigation bar
│   │   ├── Sidebar.jsx            # User list sidebar
│   │   ├── NoChatSelected.jsx     # Empty state
│   │   ├── AuthImagePattern.jsx   # Auth page decoration
│   │   ├── protectRoute.jsx       # Route guards
│   │   └── Skeletons/             # Loading skeletons
│   ├── pages/
│   │   ├── Home.jsx               # Main chat page
│   │   ├── Login.jsx              # Login page
│   │   ├── Signup.jsx             # Signup page
│   │   ├── Profile.jsx            # Profile page
│   │   └── Settings.jsx           # Theme settings
│   ├── store/
│   │   ├── authStore.js           # Auth + socket state
│   │   ├── MessageStore.js        # Messages + users state
│   │   └── ThemeStore.js          # Theme state
│   ├── lib/
│   │   ├── axiosInstance.js       # Axios config
│   │   └── utils.js               # Helper functions
│   ├── constant/
│   │   └── index.js               # Theme list
│   ├── App.jsx
│   ├── main.jsx
│   └── index.css
├── vercel.json
├── vite.config.js
└── package.json
```

---

## ⚙️ Getting Started

### Prerequisites
- Node.js >= 20
- npm or yarn
- MongoDB database
- Cloudinary account

### 1. Clone the repository

```bash
# Frontend
git clone https://github.com/shahnawaz-codes/chat-app-client.git
cd chat-app-client

# Backend (separate repo)
git clone https://github.com/shahnawaz-codes/chat-app-server.git
cd chat-app-server
```

### 2. Install dependencies

```bash
# Frontend
cd chat-app-client
npm install

# Backend
cd chat-app-server
npm install
```

### 3. Configure environment variables

**Frontend** — create `.env` in `chat-app-client/`:
```env
VITE_SERVER_URL=http://localhost:5000
```

**Backend** — create `.env` in `chat-app-server/`:
```env
PORT=5000
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret
CLIENT_URL=http://localhost:5173
```

### 4. Run the app

```bash
# Start backend
cd chat-app-server
npm run dev

# Start frontend (in a new terminal)
cd chat-app-client
npm run dev
```

Open [http://localhost:5173](http://localhost:5173) in your browser.

---

## 🌐 Deployment

### Frontend — Vercel

1. Push code to GitHub
2. Import project on [vercel.com](https://vercel.com)
3. Add environment variable: `VITE_SERVER_URL=https://your-backend.onrender.com`
4. Deploy

The `vercel.json` handles React Router redirects:
```json
{
  "rewrites": [{ "source": "/(.*)", "destination": "/index.html" }]
}
```

### Backend — Render

1. Push code to GitHub
2. Create a new **Web Service** on [render.com](https://render.com)
3. Add all backend environment variables
4. Deploy

> **Important:** Make sure your backend cookie settings use `sameSite: "none"` and `secure: true` for cross-domain authentication to work.

---

## 🔒 Authentication Flow

```
User Signup/Login
      ↓
Server validates credentials
      ↓
JWT token stored in httpOnly cookie (sameSite: none, secure: true)
      ↓
Frontend sends cookie automatically with every request (withCredentials: true)
      ↓
Server verifies token on protected routes
```

---

## 🔌 Socket.IO Events

| Event | Direction | Description |
|-------|-----------|-------------|
| `onlineUsers` | Server → Client | List of currently online user IDs |
| `newMessage` | Server → Client | New message received |

---

## 📸 Screenshots

| Login | Chat | Settings |
|-------|------|----------|
| Auth page with pattern | Real-time chat UI | 32+ theme options |

---

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/my-feature`
3. Commit changes: `git commit -m "feat: add my feature"`
4. Push: `git push origin feature/my-feature`
5. Open a Pull Request

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## 👨‍💻 Author

**Shahnawaz**
- GitHub: [@shahnawaz-codes](https://github.com/shahnawaz-codes)

---

> Built with ❤️ using React + Node.js + Socket.IO
