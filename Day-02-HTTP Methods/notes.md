# Day 02 - HTTP Methods Notes

## What are HTTP Methods?
HTTP methods (also known as HTTP verbs) indicate the desired action to be performed for a given resource. They tell the server what to do with the data.

---

## The 5 Core HTTP Methods

### 1. GET
* **Purpose:** Retrieve or fetch data from the server.
* **Characteristics:** Safe and Idempotent (running it multiple times won't change the data).
* **Support Example:** Checking a user's account details or fetching log files.

### 2. POST
* **Purpose:** Upload fresh data to the server to create a new resource.
* **Characteristics:**  Not safe or idempotent (running it numerous times will result in duplicate data).
* **Support Example:** Opening a new support request or registering a new user.

### 3. PUT
* **Purpose:** Replace a *existing* resource fully. If the resource does not already exist, it may create one..
* **Characteristics:** Idempotent (replacing the same data multiple times has the same final result).
* **Support Example:** Updating a user's entire profile information.

### 4. PATCH
* **Purpose:** Modify an existing resource (partially)..
* **Characteristics:** Usually not idempotent.
* **Support Example:** Changing a ticket's status from "Open" to "Resolved" without affecting other ticket data

### 5. DELETE
* **Purpose:** Remove data or a resource from the server.
* **Characteristics:** Idempotent (deleting something that is already deleted will still result in it being gone).
* **Support Example:** Deleting a duplicated transaction or removing an inactive user account.

---

## Why This Matters for Product Support Engineers
* **Efficient Troubleshooting:** When checking network logs (HAR files) or browser Developer Tools, knowing the HTTP method helps identify if a user was trying to view data (`GET`), submit a form (`POST`), or update something (`PUT`/`PATCH`).
* **Replicating Issues:** Helps when constructing API requests in tools like Postman to reproduce bugs reported by clients.
* **Understanding Error Codes:** Certain errors are tied to methods (e.g., a `405 Method Not Allowed` means a client tried to `POST` to an endpoint that only accepts `GET`).