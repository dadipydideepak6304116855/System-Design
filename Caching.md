
# ⚡ Caching in System Design

---

## 🔹 What is Caching?

**Caching** is the process of **storing frequently accessed data** in a **temporary storage (cache)** so that future requests can be served faster without hitting the main database or external service.

> 📌 Caching improves **response time**, **reduces load** on databases, and enhances **scalability**.

---

## 🔹 Why Use Caching?

- ✅ Reduce **latency** (faster response time)
- ✅ Decrease **database load**
- ✅ Improve **application throughput**
- ✅ Enhance **user experience**
- ✅ Save **costs** on repeated external API calls

---

## 🔹 Types of Caching

### ✅ 1. **Client-Side Cache**
- Stored in the browser (cookies, localStorage, in-memory)
- Improves frontend speed

### ✅ 2. **Server-Side Cache**
- Stored at the backend (e.g., in-memory cache like Redis)
- Avoids hitting database repeatedly

### ✅ 3. **Database Cache**
- Query results cached (e.g., MySQL Query Cache)

### ✅ 4. **CDN Cache**
- Static content cached at edge locations (images, CSS, JS)

---

## 🔹 Cache Storage Options

| Cache Type     | Tools / Tech                          |
|----------------|----------------------------------------|
| **In-Memory**  | Redis, Memcached                       |
| **Disk-based** | Ehcache, Caffeine                      |
| **Distributed**| Hazelcast, Apache Ignite, Redis Cluster|

---

## 🔹 Cache Strategies

### 🧠 1. **Read-Through Cache**

- Application reads from cache
- If not found, it fetches from DB and updates the cache

```plaintext
App → Cache → [Miss] → DB → [Update Cache]
