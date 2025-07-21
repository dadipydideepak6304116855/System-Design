
# 📇 Indexing in System Design

---

## 🔹 What is Indexing?

**Indexing** is a technique used in databases to **speed up the retrieval of data** by creating a special data structure that allows fast lookup on specific columns.

> 📌 Think of an index like a book's table of contents — it lets the system jump directly to the needed data without scanning the entire table.

---

## 🔹 Why Use Indexing?

- ✅ Accelerates query performance (especially `SELECT` statements)
- ✅ Reduces I/O overhead by minimizing full table scans
- ✅ Essential for scaling read-heavy systems
- ✅ Enables efficient filtering, sorting, and joins

---

## 🔹 How Indexing Works (High Level)

- Database creates a **B-Tree**, **Hash Table**, or similar structure
- This structure maps the **indexed column values** to the **row locations**
- When you query, the engine uses the index to jump directly to relevant rows

---

## 🔹 Types of Indexes

| Type                | Description                                                                 |
|---------------------|-----------------------------------------------------------------------------|
| **Primary Index**    | Automatically created on the primary key column                            |
| **Secondary Index**  | Manually created on non-primary columns                                    |
| **Composite Index**  | Index created on **multiple columns** (e.g., `name + age`)                  |
| **Unique Index**     | Ensures indexed values are unique                                           |
| **Partial Index**    | Indexes a subset of rows (e.g., where `is_active = true`)                   |
| **Full-text Index**  | Used for keyword search in large text fields                               |
| **Spatial Index**    | Optimized for geographic data (used in maps, coordinates, etc.)             |
| **Bitmap Index**     | Efficient for low-cardinality columns (common in OLAP systems)              |

---

## 🔹 Example (SQL)

```sql
-- Create a basic index
CREATE INDEX idx_users_email ON users(email);

-- Composite index
CREATE INDEX idx_users_name_age ON users(first_name, age);

-- Unique index
CREATE UNIQUE INDEX idx_unique_username ON users(username);
