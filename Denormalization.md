# 🧾 Denormalization in System Design

---

## 🔹 What is Denormalization?

**Denormalization** is the process of **intentionally introducing redundancy** into a normalized database schema to improve **read performance** and reduce the need for expensive **joins**.

> 📌 Denormalization trades **storage space** for **query speed** — it's a deliberate decision in read-heavy systems.

---

## 🔹 Why Use Denormalization?

- ✅ Faster read queries (especially joins)
- ✅ Fewer complex joins during runtime
- ✅ Improved performance in analytics/reporting
- ✅ Better performance in distributed databases where joins are costly

---

## 🔹 Normalization vs Denormalization

| Feature              | Normalization                         | Denormalization                          |
|----------------------|----------------------------------------|------------------------------------------|
| Goal                 | Eliminate redundancy, ensure integrity| Improve performance                      |
| Query Speed          | Slower (needs joins)                  | Faster (pre-joined data)                |
| Storage Efficiency   | High                                   | Low (redundant data)                    |
| Data Integrity       | High (less duplication)                | Risk of inconsistency                   |
| Use Case             | OLTP systems (e.g., banking)           | OLAP systems, reporting, dashboards     |

---

## 🔹 Example: Normalized vs Denormalized

### ✅ Normalized Schema

```plaintext
Users
-----
user_id | name
1       | Alice

Orders
-------
order_id | user_id | product
101      | 1       | Laptop

