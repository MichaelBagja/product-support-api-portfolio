# Day 3 - JSON Fundamentals

## What is JSON?

JSON (**JavaScript Object Notation**) is a data format that is being used between application to communicate

Almost every REST API is using JSON as a format for response and request as it is easy for human an computer to understand. 

---

## JSON Sturcture

JSON consist **object** and **array**.

Object sis using bracket `{}` and save value in the format of **key-value pair**.

Example:

```json
{
  "id": 101,
  "name": "Michael",
  "country": "Indonesia"
}
```

Explanation:

- `id`, `name`, and `country` called **key**.
- `101`, `"Michael"`, and `"Indonesia"` called **value**.
- Every key must use **double quotes ("")**.

---

## JSON Data Type

JSON have some data type that is being used

| Data Type | Example |
|-----------|---------|
| String | `"Michael"` |
| Number | `100` |
| Boolean | `true` |
| Null | `null` |
| Object | `{}` |
| Array | `[]` |

Example:

```json
{
  "name": "John",
  "age": 25,
  "verified": true,
  "phone": null
}
```

---

## Nested Object

An Object that contain another object. This kind of structure called **nested object**.

Example:

```json
{
  "customer": {
    "id": 100,
    "name": "Michael"
  }
}
```

To access customer name:

```text
customer.name
```

Nested object often used to group related information.

---

## Array

Array used to save data that is more than one

Example:

```json
{
  "products": [
    "Keyboard",
    "Mouse",
    "Monitor"
  ]
}
```

Array can also contain object.

```json
{
  "orders": [
    {
      "id": 1,
      "status": "Completed"
    },
    {
      "id": 2,
      "status": "Pending"
    }
  ]
}
```

Responses like this are very common on endpoints that return a lot of data..

---

## How to read JSON

One of the most important skill when working with API is to read JSON response

Example:

```json
{
  "status": "Pending"
}
```

to understand the status of the order, we jsut need to see the field:

```text
status
```

For nested object:

```text
customer.name
```

For array:

```text
items[0].product
```

Explanation:

- `items[0]` means taking the first data from array.
- `.product` means taking the first value from key `product`.

---

## API Response Example

A response example from an API:

```json
{
  "order_id": 10234,
  "status": "Shipped",
  "customer": {
    "name": "Michael"
  },
  "items": [
    {
      "product": "Keyboard",
      "quantity": 2
    }
  ]
}
```

Penjelasan:

- `order_id` → Unique ID from the order.
- `status` → The current order status.
- `customer` → Customer Information.
- `items` → List of the product that is purchased.
- `quantity` → The number of the product that is purchased.

---

## Most Common Mistake

### Wrong

```json
{
"name":"John",
age:25
}
```

Why is it a mistake?

Because in every **key , it must use double quotes ("")**.

### Correct

```json
{
  "name": "John",
  "age": 25
}
```

Another common mistake is to add coma in the end of the data.

### Wrong

```json
{
  "name": "John",
  "age": 25,
}
```

### Correct

```json
{
  "name": "John",
  "age": 25
}
```

---

# Summary

JSON is the most common data format that is being used by REST API to exchange information.

Understanding the JSON structure will help Product Support to:

- Read API Response.
- Find important information in API response.
- Understanding nested object and array.
- Perform troubleshooting faster.
- Improve the communication with the engineering.