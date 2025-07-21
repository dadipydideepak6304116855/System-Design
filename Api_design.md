
# 🧠 API Design in System Design

---

## 🔹 What is API Design?

**API Design** is the process of **defining how clients interact with a service**. It involves designing request/response structures, endpoints, data models, and error handling to ensure **scalability**, **maintainability**, and **clarity** in communication between distributed systems or microservices.

---

## 🔹 Goals of Good API Design

- ✅ **Clarity** – Easy to understand and use
- ✅ **Consistency** – Follows a standard pattern across endpoints
- ✅ **Scalability** – Can grow with business and tech needs
- ✅ **Versioning Support** – Handles backward compatibility
- ✅ **Security** – Protects against misuse and unauthorized access
- ✅ **Resilience** – Handles failures gracefully (timeouts, retries)

---

## 🔹 REST vs gRPC vs GraphQL (Quick Overview)

| Style      | Description                                     | Use Cases                         |
|------------|--------------------------------------------------|-----------------------------------|
| **REST**   | HTTP-based, resource-oriented (GET/POST/PUT/DELETE) | CRUD apps, Web services           |
| **gRPC**   | Binary protocol over HTTP/2, uses protobuf       | Internal microservices, low latency |
| **GraphQL**| Clients request exactly what they need           | Complex queries from frontend     |

---

## 🔹 RESTful API Design Principles

1. **Use Nouns, Not Verbs**  
   - ✅ `/users`  
   - ❌ `/getUsers`

2. **HTTP Methods Mapping**
   | Method | Purpose     |
   |--------|-------------|
   | GET    | Read data   |
   | POST   | Create data |
   | PUT    | Update data |
   | DELETE | Delete data |

3. **Use Plural Resource Names**
   - `/users`, `/products`

4. **Use Proper HTTP Status Codes**
   | Code | Meaning             |
   |------|----------------------|
   | 200  | OK                   |
   | 201  | Created              |
   | 400  | Bad Request          |
   | 401  | Unauthorized         |
   | 404  | Not Found            |
   | 500  | Internal Server Error|

5. **Versioning APIs**
   - URI versioning: `/api/v1/users`
   - Header versioning: `Accept: application/vnd.api.v1+json`

6. **Pagination**
   - `GET /users?page=2&limit=10`

7. **Filtering and Sorting**
   - `GET /products?category=books&sort=price_desc`

8. **Error Responses (JSON format)**
   ```json
   {
     "error": {
       "code": 400,
       "message": "Invalid user ID"
     }
   }
