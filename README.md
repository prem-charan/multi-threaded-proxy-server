# Multi-Threaded Proxy Server (With and Without Cache)

A high-performance proxy server implemented in C that supports multi-threading and caching.

---

## 📖 Project Overview
This project demonstrates how a proxy server handles multiple client requests efficiently using multi-threading. It also explores caching mechanisms to improve response times and reduce server load.

### ✨ Features
- Multi-threading using **POSIX threads (pthreads)**.
- **Semaphore-based synchronization** instead of condition variables.
- **LRU Cache** implementation to store and retrieve frequently accessed web pages.
- Implements basic **request forwarding** from client to server.
- Can run **with or without caching**.

---

## 🛠 How It Works

### 🌐 Proxy Server Workflow
1. The client sends an HTTP request to the proxy.
2. The proxy checks if the requested page is in the cache.
3. If cached, the data is sent to the client directly.
4. Otherwise, the proxy fetches the page from the web server, forwards it to the client, and stores it in the cache.

### 🔀 Multi-Threading Implementation
- Uses **pthreads** for concurrent handling of multiple client requests.
- **Semaphores** are used for synchronization.
- Each request runs on a separate thread to ensure non-blocking behavior.

---

## 🚀 Getting Started

### 🔧 Prerequisites
- **Linux Machine** (required for execution)
- **GCC Compiler**

### 🏗 Installation & Execution
```bash
# Clone the repository
git clone https://github.com/prem-charan/multi-threaded-proxy-server.git

# Navigate to the project directory
cd MultiThreadedProxyServerClient

# Compile the project
make all

# Run the proxy server
./proxy <port_number>

# Open in a browser:
http://localhost:<port>/https://www.youtube.com/
```

### ⚠️ Notes
- **Disable your browser cache** before testing.
- To run the proxy **without cache**, rename `proxy_server_with_cache.c` to `proxy_server_without_cache.c` in the `Makefile` and recompile.
