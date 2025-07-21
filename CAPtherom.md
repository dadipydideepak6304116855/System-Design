
# 🧠 CAP Theorem in System Design

---

## 🔹 What is CAP Theorem?

The **CAP Theorem**, also known as **Brewer’s Theorem**, states that a **distributed system** can only **guarantee** **two out of the following three** properties at the same time:

- **C**onsistency
- **A**vailability
- **P**artition Tolerance

---

## 🔹 The 3 Properties Explained

### ✅ Consistency (C)
Every read receives the **most recent write** or an error.  
➡️ All nodes return the **same data** at any given time.

### ✅ Availability (A)
Every request receives a **(non-error) response**, regardless of the current state of any node.  
➡️ The system remains **operational** 100% of the time.

### ✅ Partition Tolerance (P)
The system continues to **operate despite network failures** or message loss between nodes.  
➡️ It **tolerates network splits** and continues to function.

---

## 🔹 The CAP Trade-Off

Due to network issues, **Partition Tolerance (P)** is often **non-negotiable** in real-world systems.  
So, systems must choose between:

- **CP (Consistency + Partition Tolerance)**  
  Sacrifices Availability  
  > Example: HBase, MongoDB (in strict mode)

- **AP (Availability + Partition Tolerance)**  
  Sacrifices Consistency  
  > Example: Cassandra, Couchbase, DynamoDB

- **CA (Consistency + Availability)**  
  Assumes no partitions (ideal but unrealistic in distributed systems)  
  > Example: Traditional RDBMS (not truly distributed)

---

## 🔹 Visual Summary

   ┌───────────────┐
   │               │
   │   CAP Theorem │
   │               │
   └───────────────┘
          ▲
   ┌──────┼──────┐
   │      │      │
   │      │      │
   C      A      P



---

## 🔹 Real-World Examples

| System         | Type | Guarantees         | Sacrifices    |
|----------------|------|--------------------|---------------|
| **Cassandra**  | AP   | Availability, Partition | Consistency |
| **MongoDB** (default) | CP | Consistency, Partition | Availability |
| **HBase**      | CP   | Consistency, Partition | Availability |
| **CouchDB**    | AP   | Availability, Partition | Consistency |
| **Relational DB (not distributed)** | CA | Consistency, Availability | Partition Tolerance |

---

## 🔹 When to Choose What?

- **CP systems** are good for **banking, ledgers, inventory tracking**, etc.
- **AP systems** are better for **social media, analytics, real-time dashboards** where temporary inconsistency is acceptable.

---

## 🔹 Summary

| Property            | Description                                  |
|---------------------|----------------------------------------------|
| **Consistency**     | All nodes see the same data at the same time |
| **Availability**    | System remains responsive all the time       |
| **Partition Tolerance** | System works even when network splits occur |

> 📌 **You can’t have all three** in a real distributed system. Pick the right trade-off based on your use case.

