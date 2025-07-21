
# 🛑 Circuit Breaker in System Design

---

## 🔹 What is a Circuit Breaker?

A **Circuit Breaker** is a **resilience pattern** used in distributed systems and microservices to **prevent repeated failures** when a downstream service is unavailable or under high load.

> 📌 It acts like a **fuse** — it “breaks” the connection temporarily to protect the system from cascading failures.

---

## 🔹 Why Use a Circuit Breaker?

- ✅ Prevent system overload
- ✅ Improve fault tolerance
- ✅ Avoid cascading failures
- ✅ Enable graceful degradation
- ✅ Improve overall system stability

---

## 🔹 Circuit Breaker States

| State         | Description                                                  |
|---------------|--------------------------------------------------------------|
| **Closed**     | Everything is working fine. All requests are forwarded.      |
| **Open**       | Requests are immediately failed/skipped to protect the system. |
| **Half-Open**  | A few test requests are allowed to check if the service is back. |

---

## 🔹 State Transition Diagram

```plaintext
       +-----------+     Failure Threshold     +-----------+
       |           |-------------------------->|           |
       |  CLOSED   |                           |   OPEN    |
       |           |<--------------------------|           |
       +-----------+       Recovery Timer      +-----------+
              |                                      |
              |          Success Test                |
              |------------------------------------->|
              |               HALF-OPEN              |
              |<-------------------------------------|
              |         All Test Calls Passed        |

🔹 How It Works
Service A calls Service B.

If there are too many failures, the circuit breaker opens.

While in the open state, Service A will immediately fail fast without calling Service B.

After a cool-down period, it enters half-open state to test the connection.

If the test calls are successful, the circuit closes again. If they fail, it goes back to open.

🔹 Real-World Analogy
🛗 Imagine a hotel elevator. If it malfunctions multiple times, it's taken out of service (open state). After a repair, it's tested with a limited load (half-open). If the test is successful, it's reopened to all (closed state).
