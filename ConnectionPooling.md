
# 🔗 Connection Pooling in System Design

---

## 🔹 What is Connection Pooling?

**Connection Pooling** is a technique used to **reuse a pool of pre-established database connections**, instead of creating a new one for every client request.

> 📌 It optimizes resource usage, improves performance, and reduces latency by avoiding repeated connection setup overhead.

---

## 🔹 Why Use Connection Pooling?

- ✅ Reduces the **cost of creating and closing** database connections
- ✅ Handles **high concurrency** efficiently
- ✅ Minimizes **connection latency**
- ✅ Prevents **connection exhaustion**
- ✅ Supports **scalable** backend systems

---

## 🔹 How It Works

```plaintext
[Application Request]
        ↓
[Connection Pool Manager]
        ↓
✔ If connection available → Reuse it
✖ If none available → Wait or reject
        ↓
[Database Connection]
        ↓
[Return connection to pool after use]


🔹 Real-World Analogy
🏦 Think of a bank with a limited number of tellers (DB connections). Instead of hiring a new teller for each customer (request), customers wait for a teller to become free — that's pooling.

