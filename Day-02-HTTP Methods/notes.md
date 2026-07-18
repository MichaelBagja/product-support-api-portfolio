# Day 02 - HTTP Methods Notes

## What are HTTP Methods?
In simple terms, HTTP Methods are standardized commands or instructions sent from your device (web browser or client) to a server.

---

## The Core Methods

### 1. GET
Used to pull or get data from the server. It’s safe and idempotent, meaning you can run this command multiple times and it won't change anything on the server.
* **Example:** Checking user account details or fetching log files.

### 2. POST
Used to send new data to the server to create something new. It is NOT idempotent—if you click submit twice, you'll probably create duplicate data.
* **Example:** Creating a new support ticket or registering a user.

### 3. PUT
Used to update an existing resource by replacing the whole thing. If you change a user's profile with PUT, you have to send all the fields again, or the missing ones might get wiped out.
* **Example:** Updating a user's entire profile information.

### 4. PATCH
Similar to PUT, but it only updates specific parts of the data. You don't need to send the whole package, just the part you want to change.
* **Example:** Changing a ticket status from "Open" to "Resolved" without touching the rest of the text.

### 5. DELETE
Used to remove data from the server. Once it's gone, it's gone.
* **Example:** Deleting a duplicate transaction or removing an inactive account.

---

## Why this matters for Product Support
* **Troubleshooting:** When looking at network logs (HAR files) or DevTools, the method tells you exactly what the user was trying to do (viewing data vs submitting a form).
* **Replicating bugs:** Helpful when testing APIs in Postman to reproduce client issues.
* **Reading errors:** If you see a `405 Method Not Allowed` error, it means the client used the wrong method for that specific endpoint.