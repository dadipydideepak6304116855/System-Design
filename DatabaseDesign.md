
# 🗃️ Database Design in System Design

---

## 🔹 What is Database Design?

**Database Design** is the process of **structuring a database schema** that efficiently stores and manages data for an application or system, ensuring **scalability, integrity, and performance**.

> 📌 It involves identifying entities, defining relationships, choosing data types, indexing, normalization, and deciding between SQL vs NoSQL.

---

## 🔹 Goals of Good Database Design

- ✅ Data consistency and integrity
- ✅ High performance (query & write efficiency)
- ✅ Scalability for future growth
- ✅ Easy maintainability
- ✅ Support for business logic

---

## 🔹 Key Components

| Component        | Description |
|------------------|-------------|
| **Entities**     | Core objects (e.g., User, Order, Product) |
| **Attributes**   | Properties of entities (e.g., name, price) |
| **Relationships**| Associations between entities (e.g., User has Orders) |
| **Schema**       | Blueprint of tables/collections |
| **Constraints**  | Rules like primary keys, foreign keys, uniqueness |

---

## 🔹 Step-by-Step Process

### 1. **Requirement Analysis**
- Understand what data needs to be stored
- Know access patterns (reads/writes/updates)

### 2. **Identify Entities and Relationships**
- Use ERD (Entity-Relationship Diagram)
- Examples: `User`, `Order`, `Product`, `Payment`

### 3. **Define Tables or Collections**
- For SQL: Create normalized tables
- For NoSQL: Design based on access patterns

### 4. **Choose SQL vs NoSQL**

| Criteria       | SQL (Relational DB)     | NoSQL (Document, Key-Value, etc.) |
|----------------|--------------------------|------------------------------------|
| Schema         | Fixed (strict schema)    | Flexible / schema-less             |
| Transactions   | Strong ACID support      | BASE (eventual consistency)        |
| Use Case       | Structured data, joins   | High-scale, semi/unstructured data |
| Examples       | MySQL, PostgreSQL        | MongoDB, Cassandra, DynamoDB       |

### 5. **Normalize or Denormalize**
- Use **Normalization** (1NF → 3NF) to remove redundancy
- Use **Denormalization** for performance in read-heavy systems

### 6. **Indexing**
- Add indexes on frequently queried fields
- Use compound indexes for multi-field queries

### 7. **Define Keys**
- **Primary Key**: Uniquely identifies a record
- **Foreign Key**: Links one table to another
- **Composite Key**: Multiple columns as a key

### 8. **Handle Data Types & Constraints**
- Use appropriate types (e.g., `int`, `varchar`, `timestamp`)
- Apply `NOT NULL`, `UNIQUE`, `DEFAULT`, etc.

---

## 🔹 Entity-Relationship Example

```plaintext
User (user_id, name, email)
Order (order_id, user_id, product_id, date)
Product (product_id, name, price)

Relationships:
- User has many Orders (1:N)
- Order has one Product (N:1)
