
# 🌐 CDN (Content Delivery Network) in System Design

---

## 🔹 What is a CDN?

A **Content Delivery Network (CDN)** is a geographically distributed network of servers that **cache and deliver content** (e.g., HTML, CSS, JavaScript, images, videos) to users based on their location.

> 🔁 CDNs reduce latency and improve load times by serving content from the **nearest edge server** rather than the origin server.

---

## 🔹 Why Use a CDN?

- ✅ **Faster content delivery**
- ✅ **Reduced latency and load time**
- ✅ **Offloads traffic from origin servers**
- ✅ **Improved scalability during traffic spikes**
- ✅ **Better availability and reliability**
- ✅ **Enhanced DDoS protection and security**

---

## 🔹 How It Works

1. User requests a resource (e.g., `image.jpg`)
2. Request goes to the nearest **edge server**
3. If cached:
   - ✅ Served directly from the edge
4. If not cached:
   - ❌ Edge server fetches from origin, caches it, and serves the response

---

## 🔹 Real-World Analogy

> Think of a CDN as a network of **local grocery stores** instead of one **central warehouse**. You go to the closest store (edge server) instead of waiting for delivery from the central warehouse (origin server).

---

## 🔹 Types of Content Served

- **Static Content**:
  - HTML, JS, CSS, images, fonts
- **Dynamic Content** (with advanced CDN setups):
  - API responses, personalized data
- **Streaming Content**:
  - Videos, live streams

---

## 🔹 Popular CDN Providers

| Provider              | Features                              |
|-----------------------|----------------------------------------|
| **Cloudflare**        | Global CDN, DDoS protection, DNS       |
| **Akamai**            | Enterprise-grade, advanced security    |
| **Amazon CloudFront** | Integrates with AWS, scalable          |
| **Fastly**            | Edge computing, real-time caching      |
| **Google Cloud CDN**  | Integrated with Google Cloud Platform  |

---

## 🔹 Key Concepts

### ✅ Edge Server
Server located closer to the user that caches and serves content.

### ✅ Cache-Control Headers
Defines how and how long content should be cached:
```http
Cache-Control: public, max-age=86400
