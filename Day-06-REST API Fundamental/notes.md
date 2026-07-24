# REST API Fundamentals

## Apa itu REST API?

REST (**Representational State Transfer**) is a *architectural style* that is used to build API so apps can communicate via HTTPS protocol 

REST **is not a programing language** and **not a framework**. REST is a bunch of rules (*constraints*) that makes the communication between client and server become more simple, consistent, dan easy to develop.

---

## REST API Analogy

Imagine a restaurant.

| Real World | REST API |
|------------|----------|
| Customer | Client |
| Waiter | API |
| Chef | Backend |
| Kitchen | Database |

The flow in a simple way:

```text
Customer
    │
Ordering food
    │
Waiter (REST API)
    │
Chef (Backend)
    │
Database
```

Just like customer who doesn't need to know how the food is made, client also doesn't need to know how server proccessing data.

Client just need to send **request**, then receive **response**.

---

# Why we use REST API?

- Seperate frontend dan backend.
- Easy to develop.
- Using HTTP Standard.
- Can be used by various platforms.
- Easy to learn.

---

# REST Architecture

```text
Client
   │
HTTP Request
   │
REST API
   │
Business Logic
   │
Database
   │
HTTP Response
   │
Client
```

### Flow

1. Client send request.
2. REST API receive request.
3. Backend proccess request.
4. Database return the data.
5. Server send response.

---

# REST Constraints

REST have six main rules.

## 1️⃣ Client-Server

Client responsible for the interface (*UI*), while server responsible to manage data.

---

## 2️⃣ Stateless

Server **did not remember the previous request**.

Every request need to carry every needed information.

### Example

First Request 

```http
GET /users/1
```

Second Request 

```http
GET /orders
```

Server will take both request as a new request.

---

## 3️⃣ Cacheable

Response can be temporarily saved (*cache*) so the next request can be faster.

---

## 4️⃣ Uniform Interface

REST have a consistent and standaed communication.

Example:

- Resource is using URL.
- Using HTTP Method.
- Format response is consistent.

---

## 5️⃣ Layered System

The client does not know how many layers the request passes through..

```text
Client
   │
Load Balancer
   │
API Gateway
   │
Backend
```

---

## 6️⃣ Code on Demand (Opsional)

Server can send the code that is run by the client.

This constraint is optional.

---

# Resource

Resource is the data that is exist in API.

Example:

```text
/users
/products
/orders
```

Use **noun**.

✅ Correct

```text
/users
/products
```

❌ Wrong

```text
/getUsers
/createProduct
```

---

# Endpoint

Endpoint is the address that is use to access a specific resource

```http
GET /users
GET /users/1
POST /users
PUT /users/1
PATCH /users/1
DELETE /users/1
```

---

# HTTP Methods

| Method | Function |
|---------|--------|
| GET | Get data |
| POST | Create data |
| PUT | Update overall data |
| PATCH | Change part of the data |
| DELETE | Delete data |

---

# HTTP Status Code

| Code | Description |
|------|------------|
| 200 | OK |
| 201 | Created |
| 204 | No Content |
| 400 | Bad Request |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |
| 409 | Conflict |
| 422 | Unprocessable Entity |
| 429 | Too Many Requests |
| 500 | Internal Server Error |
| 502 | Bad Gateway |
| 503 | Service Unavailable |

---

# Request Component

## URL

```http
GET /users/15
```

## Headers

```http
Authorization: Bearer <token>
Content-Type: application/json
Accept: application/json
```

## Path Parameter

```http
GET /users/15
```

Number  **15** is the path parameter.

## Query Parameter

```http
GET /users?page=2&limit=20
```

## Request Body

```json
{
  "name": "Michael",
  "email": "michael@example.com"
}
```

---

# Response Component

## Status

```http
200 OK
```

## Headers

```http
Content-Type: application/json
```

## Body

```json
{
  "id": 1,
  "name": "Michael",
  "email": "michael@example.com"
}
```

---

# JSON

### Object

```json
{
  "name": "Michael",
  "age": 25
}
```

### Array

```json
[
  {
    "id": 1
  },
  {
    "id": 2
  }
]
```

### Nested Object

```json
{
  "user": {
    "name": "Michael",
    "email": "michael@example.com"
  }
}
```

---

# Idempotency

The same request results in the same final condition.

### GET Example

```http
GET /users/1
```

### DELETE Example

```http
DELETE /users/1
```

---

# REST API Example 

### Request

```http
GET /products
```

### Response

```json
[
  {
    "id": 1,
    "title": "Laptop",
    "price": 15000000
  }
]
```

### Status

```http
200 OK
```

---

# 🚨 Error yang Sering Ditemui

| Status | Reason |
|---------|----------|
| **400** | Invalid request |
| **401** | Invalid Token or Have not login yet |
| **403** | No access |
| **404** | Endpoint not found |
| **429** | Rate limit |
| **500** | Sever Error |

---

# Product Support Perspective

The REST API understadning will help Product Suppor to:

- To identify wheter the problem is from client or server.
- Understand every HTTP Status Code meaning.
- Checking customer request.
- Make sure the right endpoint is being used.
- Performing troubleshooting before escalating case to the engineering team.

---

# Summary

REST API is a communication standard used by various applications.

Concepts to understand:

- REST Architecture
- REST Constraints
- Resource
- Endpoint
- HTTP Methods
- HTTP Status Code
- Request & Response
- JSON
- Idempotency

