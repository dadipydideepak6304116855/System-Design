# 🕒 Latency in System Design

---

## 🔹 What is Latency?

**Latency** refers to the **time delay** between a user's action (or a request) and the system’s corresponding response.

> 📌 It is typically measured in **milliseconds (ms)** and is a key factor in **performance, user experience, and scalability** of any system.

---

## 🔹 Types of Latency

| Type                | Description                                                                |
|---------------------|----------------------------------------------------------------------------|
| **Network Latency** | Time taken for a data packet to travel between client and server           |
| **Disk Latency**    | Time taken to read/write data to disk or SSD                               |
| **Processing Latency** | Time taken by the server/service to process a request                  |
| **Queueing Latency**| Time spent in message queues or buffers before processing                  |
| **Database Latency**| Delay in fetching/updating data in a database                              |
| **Application Latency** | Total time the user waits for a complete response                     |

---

## 🔹 How to Measure Latency

- ✅ **End-to-End latency**: Time from request sent to response received
- ✅ **Round-trip time (RTT)**: Time for a signal to go to the destination and back
- ✅ Tools:
  - Browser Dev Tools (for frontend apps)
  - `ping`, `traceroute`, `curl -w`
  - Monitoring platforms (Datadog, Prometheus, New Relic)

---

## 🔹 Acceptable Latency Benchmarks

| Use Case                   | Acceptable Latency     |
|----------------------------|------------------------|
| Web page load              | < 200 ms (ideal)       |
| API call                   | 50–300 ms              |
| Real-time chat/game        | < 100 ms               |
| Video streaming            | < 3000 ms (buffered)   |
| Trading / Financial apps   | < 10 ms                |

---

## 🔹 Causes of High Latency

- 🌐 Slow or congested network
- 🧱 Heavy database joins or large queries
- 🔁 Synchronous chaining of services
- 📦 Large payloads or uncompressed responses
- 💤 Thread blocking or I/O wait
- 🌍 Long geographical distance (cross-region traffic)

---

## 🔹 How to Reduce Latency

| Strategy                     | Description                                                  |
|-----------------------------|--------------------------------------------------------------|
| **Caching**                 | Use Redis, Memcached to avoid recomputation or DB hits       |
| **CDN**                     | Serve static assets closer to users                          |
| **Database Indexing**       | Optimize queries with proper indexes                         |
| **Asynchronous Processing** | Offload long tasks to background jobs or queues              |
| **Data Compression**        | Use gzip or Brotli for smaller network payloads              |
| **Connection Pooling**      | Reuse open connections instead of creating new ones          |
| **Minimize Round Trips**    | Aggregate data or batch requests                             |
| **Load Balancing**          | Distribute traffic to prevent service bottlenecks            |
| **Edge Computing**          | Move computation closer to users                             |

---

## 🔹 Latency vs Throughput

| Metric        | Description                                           |
|---------------|-------------------------------------------------------|
| **Latency**   | Time taken to respond to a single request             |
| **Throughput**| Number of requests handled per second (RPS/QPS)       |

> 📌 **Low latency** ≠ **High throughput** — they often require different optimization strategies.

---

## 🔹 Monitoring Latency

| Metric                  | Use                                              |
|--------------------------|--------------------------------------------------|
| **P50 (Median)**         | Typical experience                              |
| **P95/P99 Latency**      | Tail latency — important for identifying outliers|
| **Average Response Time**| Useful for trends, not outliers                 |
| **Timeout Errors**       | Indicates when latency exceeds acceptable levels|

---

## 🔹 Summary

| Topic             | Description                                   |
|-------------------|-----------------------------------------------|
| **Latency**        | Delay between request and response           |
| **Measured In**    | Milliseconds (ms)                            |
| **Optimized With** | Caching, CDN, indexing, async, compression   |
| **Monitoring**     | Use P50/P95/P99 to track system performance  |

> 🧠 Latency is critical for delivering **fast, reliable, and user-friendly applications**. Optimizing it requires a full-stack, end-to-end view of your system.

