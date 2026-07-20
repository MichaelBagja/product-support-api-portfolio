# Day 2 - HTTP Headers & Authentication    

Headers is an additional information that is being send along with request or response

Headers is not included with the primary data but only to provide information so client and server can communicate

Example:
- What is the format of the data that is being sent?
- Authentichation information
- App info that is sending the request

---

## Header that is always being used

### Content Type

This header providing information of what data format that is being sent

Example:

'''http
Content-Typle: application/json
'''

It means that the server read the data in the format of JSON

---

### Authorization

This header being use to pove that the client have the permisiion to access API

Example:

'''https
Authorization: Bearer *your_token*
'''

If the token that is used is not valid, it will show error **401 Unauthorized**.

---

### User - Agent

This providing information of what app server that is sending the request

Example:

```http
User-Agent: PostmanRuntime/7.45.0
```

Meaning that postman sending the request

---

### API Authenthication

Authentication itself is a prccess to make sure who is accesing the API

Methods to do this is as follows:

- API KEY
- Bearer Token

---

## API Key

This is a unique code that is being given to an app

It looks like this:

```http
x-api-key: abc123xyz
```

---

## Bearer Token

This is a token that we can get after being able to login and can be send after every request

Example: 


```http
Authorization: Bearer eyJhbGciOiJIUzI1Ni...
```

---

## The Difference between API Key and Bearer Token

## Perbedaan API Key dan Bearer Token

| API Key | Bearer Token |
|---------|--------------|
| Identify App | Identify user |
| More simple | More save |
| No expiration | Can be expired |
| Using header `x-api-key` | Using header `Authorization` |

---
