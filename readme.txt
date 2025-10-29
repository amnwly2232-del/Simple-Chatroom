# 💻 Assignment 04: Simple Chatroom using Go RPC

This project implements a simple chatroom application using **Go's built-in Remote Procedure Call (RPC)** package, fulfilling the requirements of the assignment.

The solution is split into a **Server (`server.go`)** that stores messages and a **Client (`client.go`)** that handles user interaction.

---

## 🚀 How to Run the Application

The application requires two main components running concurrently: the server and at least one client.

### 🧩 Prerequisites
- Go (Golang) must be installed on your system.

---

### 1️⃣ Start the Server (`server.go`)
Open the first terminal window and run:

```bash
go run server.go
```

🟢 The server will start listening on **port 1234** and will log all incoming messages.

---

### 2️⃣ Start the Client(s) (`client.go`)
Open one or more additional terminal windows for the clients. For each client, run:

```bash
go run client.go
```

You will be prompted to enter a username.  
The client will run until you type **`exit`** or press **Ctrl+C**.

---

## 💬 Interaction

- Clients use `bufio.NewReader(os.Stdin)` to read the entire message (including spaces).
- Each time a message is sent, the client displays the **entire chat history** (fetched from the server in the same RPC call).

---

## ⚙️ Implementation Details

**Server (`server.go`)**
- Registers the `Chat` service.
- Uses a slice (`messages []Message`) and a mutex (`sync.Mutex`) to store and protect chat history.

**RPC Mechanism**
- `Chat.SendMessage` RPC method stores the new message and returns the full, updated chat history to the client.
- This satisfies the requirement for the server to return history when a message is sent.

---

## ▶️ Running Application Video

🎥 **Link to video demo:**  
[Click to watch on Google Drive](https://drive.google.com/file/d/1AsrOrD4nc0tAwMlzkjzOqeVIBfk4ZAFE/view?usp=sharing)

