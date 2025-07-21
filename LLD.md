
# 🛠️ Low-Level Design (LLD) in System Design

---

## 🔹 What is LLD?

**Low-Level Design (LLD)** focuses on the **detailed internal design of system components**, including class diagrams, method signatures, database schema, and logic flow.

> 📌 It translates **High-Level Design (HLD)** into technical blueprints that developers use to **write code**.

---

## 🔹 Purpose of LLD

- ✅ Provide a **blueprint for developers**
- ✅ Define classes, methods, and interfaces
- ✅ Specify detailed logic and design patterns
- ✅ Create a maintainable and testable architecture
- ✅ Clarify component responsibilities and interactions

---

## 🔹 Key Elements of LLD

| Element                  | Description                                            |
|--------------------------|--------------------------------------------------------|
| **Class Diagrams**        | Relationships and responsibilities of classes          |
| **Method Signatures**     | Input/output structure for functions                   |
| **Database Schema**       | Tables, indexes, relationships                         |
| **Design Patterns**       | Usage of patterns like Singleton, Factory, Strategy    |
| **Object Models**         | Detailed object relationships and dependencies         |
| **Interface Contracts**   | API definitions and interaction details                |
| **Sequence Diagrams**     | Order of method calls between components               |

---

## 🔹 HLD vs LLD

| Feature          | HLD (High-Level Design)                      | LLD (Low-Level Design)                        |
|------------------|-----------------------------------------------|------------------------------------------------|
| **Scope**         | System-wide architecture                     | Component/class-level design                   |
| **Audience**      | Architects, leads, stakeholders              | Developers and engineers                       |
| **Details**       | Abstract, modular                            | Detailed code blueprint                        |
| **Includes**      | Tech stack, APIs, component diagrams         | Classes, DB schema, object interaction         |

---

## 🔹 LLD Example: Food Delivery App (Order Service)

### 📦 Classes

```java
class Order {
  String orderId;
  User customer;
  List<Item> items;
  Payment payment;

  void placeOrder();
  void cancelOrder();
}
