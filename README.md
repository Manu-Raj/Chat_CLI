# 💬 Chat_CLI – Multi-Client Terminal Chat Application

A cross-platform **command-line chat system written in C** that allows multiple clients to communicate in real time through a central server using TCP sockets. Built as a **team project (4 members)** to explore low-level networking, concurrency, and system programming.

---

## 🚀 Features

- 🔐 **Server-side password authentication**
- 💬 **Real-time message broadcasting** between connected clients
- 🧵 **Multithreaded client handling** (concurrent connections)
- 🌍 **Cross-platform support** (Windows & Linux)
- 🧩 Modular **socket utility layer** for cleaner networking code
- 🖥️ Fully terminal-based — lightweight and fast

---

## 🧠 How It Works

1. The **server** listens for incoming TCP connections.
2. A **client connects** and sends a password.
3. If authentication succeeds:
   - Client joins the chat room
   - Messages sent by any client are broadcast to others
4. Each client runs:
   - One thread to **send messages**
   - One thread to **receive messages**

---

## 🛠 Tech Stack

| Component | Technology |
|-----------|------------|
| Language | C |
| Networking | TCP/IP Sockets |
| Windows Support | Winsock |
| Linux/Unix Support | POSIX Sockets |
| Concurrency | pthreads |
| Build Tools | GCC / MinGW |

---

## 📂 Project Structure

```
Chat_CLI/
│
├── server.c        # Chat server logic
├── client.c        # Client-side program
├── socketutil.c    # Socket helper functions
├── socketutil.h    # Socket utility header
```

---

## ⚙️ Setup & Compilation

### 🔹 Linux / macOS

**Compile Server**
```bash
gcc server.c socketutil.c -o server -lpthread
```

**Compile Client**
```bash
gcc client.c socketutil.c -o client -lpthread
```

---

### 🔹 Windows (MinGW)

```bash
gcc server.c socketutil.c -o server -lws2_32 -lpthread
gcc client.c socketutil.c -o client -lws2_32 -lpthread
```

---

## ▶️ Running the Application

**Step 1 — Start Server**
```bash
./server
```

**Step 2 — Start Client (in another terminal)**
```bash
./client
```

**Default Settings**
- Server IP: `127.0.0.1`
- Port: `2000`
- Password: `secret123`
