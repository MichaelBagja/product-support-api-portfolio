# Day 3 - HTTP Status Codes Notes       

Status codes help us to identify where the problem happens. Whether from client side (*Client Error*) or from our side (*Server Error*)

---

## Breakdown & Troubleshooting Guide Example

### 2xx Success (Request Success)
* **`200 OK`**: The request is successful. Usually if we use requests such as 'GET', 'PUT', or 'PATCH'
* **`201 Created`**: Appears when creating a new resource. Usually appears when using request 'POST' (ex: registering new user, new transaction input)

---

### 4xx Client Error (Error from Client Side)
In general, this happens because there is a problem from the request sender side

#### 1. `400 Bad Request`
* **Reason:** The wrong format of JSON or Payload was sent, missing field in the request, or data type is not aligned
* **Support Steps:** We need the request body log to check whether the data is aligned with the API Spec

#### 2. `401 Unauthorized`
* **Reason:** User is not authenticated (have not logged in, expired token, or header 'Authorization' was not sent)
* **Support Steps:** We need to ask user to relogin or generate new API Key

#### 3. `403 Forbidden`
* **Reason:** After successfully logging in, user was not granted access to the related endpoint
* **Support Steps:** We need to check in the database or admin dashboard whether this user has access or not

#### 4. `404 Not Found`
* **Reason:** Either the data does not exist in the database or there is a typo in writing the URL endpoint
* **Support Steps:** Double check if the writing is correct

---

### 5xx Server Error (Error from Our Side)

In general, there is nothing wrong from client side. The request was sent but our internal server is having a problem and is not able to process this properly

#### `500 Internal Server Error`
* **Reason:** There is a bug in the internal server or downtime
* **Support Steps:** Escalate to engineering team by providing the needed evidence

---

In general there are so many status codes that I didn't mention here because of the number. 

I don't remember every single one of them and will only use them if there is an issue

Here is the link of a good article that I use for reference: 

https://blog.postman.com/what-are-http-status-codes/

---

## 💡 Example JSON Response (Status 401)

```json
{
  "status": "error",
  "code": 401,
  "message": "Invalid or expired API Key provided.",
  "timestamp": "2026-07-20T10:00:00Z"
}