
# ⚙️ CQRS (Command Query Responsibility Segregation)

---

## 🔹 What is CQRS?

**CQRS** stands for **Command Query Responsibility Segregation**.

It is a system design pattern that **separates read operations (queries)** from **write operations (commands)** into **distinct models**. This allows **independent scaling, optimization, and evolution** of read and write sides of an application.

---

## 🔹 Core Idea

> Instead of using the same model to handle both read and write operations, split them into:
> 
> - **Command Model** – Handles **writes** (Create, Update, Delete)
> - **Query Model** – Handles **reads** (Read only, no state change)

---

## 🔹 Why Use CQRS?

- ✅ Optimized read/write performance
- ✅ Enables **scalable** and **event-driven** architectures
- ✅ Easier to **enforce security and validation** on write side
- ✅ Allows **event sourcing** and audit trails
- ✅ Facilitates **complex business logic** on write side

---

## 🔹 Basic CQRS Flow

```plaintext
[Client]
   ↓
[Command API]  →  [Write Model]  →  [Database (writes)]
                         ↓
                    [Event Store / Message Queue]
                         ↓
[Query Model] ← [Read Database (optimized for queries)] ← [Query API]
   ↑
[Client]
