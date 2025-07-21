
# 🩺 Health Checks in System Design

---

## 🔹 What are Health Checks?

**Health checks** are mechanisms used to determine whether a service, application, or component is **operational and functioning correctly**.

> 📌 They help load balancers, orchestrators (like Kubernetes), and monitoring tools know whether to route traffic, restart a pod, or alert a team.

---

## 🔹 Why Are Health Checks Important?

- ✅ Ensure **system reliability and availability**
- ✅ Automatically detect and replace failed components
- ✅ Prevent traffic from reaching unhealthy services
- ✅ Enable auto-scaling and self-healing infrastructure
- ✅ Improve user experience by avoiding broken services

---

## 🔹 Types of Health Checks

| Type           | Description                                                                 |
|----------------|-----------------------------------------------------------------------------|
| **Liveness Check** | Checks if the app is **alive** (running in memory)                         |
| **Readiness Check**| Checks if the app is **ready** to accept traffic                           |
| **Startup Check**  | (K8s-specific) Checks if the app has **started properly** before liveness kicks in |

---

## 🔹 Liveness vs Readiness

| Feature     | Liveness                         | Readiness                          |
|-------------|----------------------------------|-------------------------------------|
| Purpose     | Detect deadlocks, memory leaks   | Prevent traffic to unready apps     |
| Failure Action | Kills and restarts container     | Stops sending traffic (no restart)  |
| Use Case    | Self-healing                     | Traffic control during init or overload |

---

## 🔹 Example Endpoints

```http
GET /health/liveness     → 200 OK if app is alive
GET /health/readiness    → 200 OK if app is ready to serve
GET /health/startup      → 200 OK if app started properly

In Spring Boot:
management:
  endpoints:
    web:
      exposure:
        include: health
