
# 📋 Non-Functional Requirements (NFRs)

## ✅ What are Non-Functional Requirements?

**Non-Functional Requirements** define **how** a system behaves rather than **what** it does.  
They focus on the **quality attributes** of a system such as performance, reliability, scalability, and security.

> They don’t describe features or functions, but rather the *constraints* and *standards* the system must meet.

---

## 🧱 Examples of Non-Functional Requirements

| Category           | Example Requirement                                             |
|--------------------|------------------------------------------------------------------|
| ⚡ Performance       | System should respond within 200ms for 95% of requests.         |
| 📈 Scalability       | System should handle 10x increase in load without degradation.  |
| 🕒 Availability      | System should be available 99.99% of the time.                 |
| 🔁 Reliability       | System should recover from failure within 2 minutes.           |
| 🔒 Security          | All data must be encrypted in transit and at rest.             |
| 📊 Observability     | Logs and metrics should be collected and centralized.          |
| 🛠 Maintainability   | System updates should not require full downtime.                |
| 🔧 Configurability   | Admins should be able to change thresholds without redeploy.    |
| 📤 Throughput        | Must handle 1,000 transactions per second.                     |
| 💾 Storage           | Should store data for at least 7 years to meet compliance.     |
| 🌐 Compatibility     | Must support Chrome, Firefox, and Safari browsers.             |
| 📱 Usability         | Mobile users must be able to complete checkout in 3 steps.     |

---

## 🔍 Why Are NFRs Important?

- Ensure the system is **usable, efficient, and resilient** under real-world conditions.
- Avoid costly issues after deployment (e.g., slow apps, data breaches).
- Guide architectural decisions during **system design**.
- Help with **compliance, SLAs, and customer trust**.

---

## 🧠 Real-World Scenario

> Suppose you're designing an e-commerce app:
- **Functional Requirement**: The system must allow users to place orders.
- **Non-Functional Requirements**:
  - Handle 5000 concurrent users.
  - Process each order within 2 seconds.
  - Ensure zero data loss during failure.

---

## 🎯 How to Define Good NFRs

Use the **SMART** approach:
- **S**pecific
- **M**easurable
- **A**chievable
- **R**ealistic
- **T**ime-bound

✅ Bad: “System should be fast.”  
✅ Good: “System should respond within 300ms for 95% of API requests under peak load.”

---

## 📌 Summary

> Non-Functional Requirements are essential to building **robust**, **secure**, and **scalable** systems.  
They define the *quality goals* and *operational expectations* that help shape system architecture and design choices.

---
