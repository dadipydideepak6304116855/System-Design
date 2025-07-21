
# 🔁 Failover in System Design

---

## 🔹 What is Failover?

**Failover** is the **automatic switching of a system to a standby or backup component** (server, database, network, etc.) when the primary component fails or becomes unavailable.

> 📌 The goal is to ensure **high availability (HA)** and **minimal downtime** during failures.

---

## 🔹 Why is Failover Important?

- ✅ Maintains **system availability** during failures
- ✅ Minimizes **downtime** and service disruption
- ✅ Essential for **mission-critical applications**
- ✅ Meets **SLA (Service Level Agreement)** targets
- ✅ Helps in disaster recovery and business continuity

---

## 🔹 Failover vs Fallback

| Term       | Description                                        |
|------------|----------------------------------------------------|
| **Failover** | Switch from primary to backup system automatically |
| **Fallback** | Switch back to the original (primary) system once it's restored |

---

## 🔹 Types of Failover

### 1. **Active-Passive**
- Only one active system at a time
- Backup remains idle until needed

```plaintext
Primary DB (Active) → Fails → Standby DB (Passive) becomes Active
