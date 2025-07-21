
# 🧩 Data Sharding in System Design

---

## 🔹 What is Data Sharding?

**Data Sharding** is a **database partitioning technique** where large datasets are split into **smaller, more manageable pieces called "shards"**, and each shard is stored separately (often on different servers or nodes).

> 📌 The goal is to **improve performance, scalability, and availability** by distributing the data horizontally.

---

## 🔹 Why Use Sharding?

- ✅ Handles **large-scale data volumes**
- ✅ Improves **query performance** and **latency**
- ✅ Enables **horizontal scaling**
- ✅ Reduces **storage and compute bottlenecks**
- ✅ Isolates failures to specific shards

---

## 🔹 Real-World Analogy

> 📚 Think of a library where books are organized alphabetically across different rooms. If all books were in one room, finding one would be slow. Splitting by category (sharding) makes the search faster.

---

## 🔹 Types of Sharding

### 1. Horizontal Sharding

- Split **rows** of a table across different shards
- Each shard contains a subset of the data

```plaintext
User Table
------------
Shard 1 → Users with ID 1–10000
Shard 2 → Users with ID 10001–20000


2. Vertical Sharding
Split columns or tables by functionality

Each shard handles specific features/modules

plaintext
Copy
Edit
Shard 1 → User Profiles Table  
Shard 2 → Orders Table  
Shard 3 → Payments Table

3. Geographic / Regional Sharding
Shard data based on geography

plaintext
Copy
Edit
US Users   → US Shard  
EU Users   → EU Shard  
APAC Users → APAC Shard


🔹 Sharding Key
A sharding key determines how data is distributed across shards.

Examples:

user_id

tenant_id

region

email (hashed)

