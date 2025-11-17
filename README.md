# Google Docs Clone (MERN + Quill + Socket.IO)

A real-time collaborative text editor built using the **MERN stack**, **Quill.js**, and **Socket.IO**. Multiple users can edit the same document simultaneously. All content is synced in real time and persisted in **MongoDB**.

---

## 🚀 Tech Stack

### **Frontend**

* **React.js** – UI framework
* **Quill.js** – Rich text editor for the document
* **Socket.IO Client** – Real-time updates
* **React Router** – Document routing by ID

### **Backend**

* **Node.js + Express** – REST API + Socket.IO server
* **MongoDB** (Mongoose) – Database for storing documents
* **Socket.IO** – Bidirectional real-time communication

---

## 🧠 How It Works

### **1. Document Loading**

When a user opens a document URL (e.g., `/documents/:id`), the backend retrieves the corresponding document from MongoDB and loads it into the editor.

### **2. Real-Time Collaboration**

* Each user connects to a Socket.IO room based on the document ID.
* As users type, Quill emits *delta changes*.
* These deltas are sent to the server through Socket.IO.
* The server broadcasts them to all other clients in the same room.

### **3. Auto-Save Mechanism**

The backend periodically saves the full document content into MongoDB, ensuring persistence even if users disconnect.

---

## 📂 Project Structure (Typical)

```
root/
│── client/             # React frontend
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   └── quill setup
│
│── server/             # Express backend
│   ├── models/
│   ├── routes/
│   ├── socket.js
│   └── server.js
│
└── package.json
```

---

## 🛠️ Installation & Setup (Local Machine)

### **Prerequisites**

* Node.js installed
* MongoDB running locally or a MongoDB Atlas URL

---

## 🔧 Backend Setup

```bash
cd server
npm install
```

Create a `.env` file:

```
MONGO_URL=mongodb://localhost:27017/gdocs-clone
PORT=5000
```

Start backend:

```bash
npm start
```

---

## 💻 Frontend Setup

```bash
cd client
npm install
npm start
```

The frontend runs on: **[http://localhost:3000](http://localhost:3000)**

---

## 🧪 Using the App

1. Start frontend + backend.
2. Visit a URL like:

```
http://localhost:3000/documents/12345
```

3. Open the same URL in multiple tabs or devices to test real-time syncing.

---

## ✨ Features

* Real-time collaborative editing
* Rich-text formatting with Quill.js
* Auto-save documents in MongoDB
* Document-based routing
* WebSocket communication using Socket.IO

---

## 📌 Future Improvements

* Add authentication
* Add document listing dashboard
* Add version history
* Add comments/highlights

---
## 📌 Clone in action
<img width="1876" height="1071" alt="image" src="https://github.com/user-attachments/assets/3007f1e3-c9a1-465e-a39b-157298a2068c" />

