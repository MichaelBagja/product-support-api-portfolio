# Day 2 - HTTP Headers & Authentication

Headers are additional information that is sent along with a request or response.

Headers are not part of the primary data. They only provide information so the client and server can communicate.

Example:
- What is the format of the data being sent?
- Authentication information
- App information that is sending the request

---

## Headers that are commonly used

### Content-Type

This header provides information about the format of the data being sent.

Example:

```http
Content-Type: application/json
```

It means that the server reads the data in JSON format.

---

### Authorization

This header is used to prove that the client has permission to access the API.

Example:

```http
Authorization: Bearer your_token
```

If the token being used is not valid, the server will return a **401 Unauthorized** error.

---

### User-Agent

This header provides information about which application is sending the request.

Example:

```http
User-Agent: PostmanRuntime/7.45.0
```

Meaning that Postman is sending the request.

---

### API Authentication

Authentication is the process of making sure who is accessing the API.

Common authentication methods include:

- API Key
- Bearer Token

---

## API Key

This is a unique code that is given to an application.

It looks like this:

```http
x-api-key: abc123xyz
```

---

## Bearer Token

This is a token that can be obtained after logging in and can be sent with every request.

Example:

```http
Authorization: Bearer eyJhbGciOiJIUzI1Ni...
```

---

## The Difference Between API Key and Bearer Token

| API Key | Bearer Token |
|---------|--------------|
| Identifies the application | Identifies the user |
| Simpler | More secure |
| No expiration | Can expire |
| Uses the `x-api-key` header | Uses the `Authorization` header |

---