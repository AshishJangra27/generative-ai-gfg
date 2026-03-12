# Working with APIs – Developer Guide

This guide explains how developers **interact with APIs (Application Programming Interfaces)**.  
APIs allow applications to **communicate with external services, databases, or other systems over the internet**.

---

# 1. What is an API?

An **API (Application Programming Interface)** is a system that allows two applications to communicate with each other.

Example:

```
Client Application → API → Server
```

Example use cases:

- Fetch weather data
- Get stock prices
- Authenticate users
- Send payments
- Access machine learning models

Example API request:

```
GET https://api.example.com/users
```

---

# 2. HTTP Methods Used in APIs

APIs commonly use **HTTP methods** to define actions.

| Method | Purpose | Example |
|---|---|---|
| GET | Retrieve data | Get user list |
| POST | Create new data | Create user |
| PUT | Update entire resource | Update profile |
| PATCH | Update partial resource | Update email |
| DELETE | Remove resource | Delete user |

Example:

```
GET /users
POST /users
DELETE /users/10
```

---

# 3. API Request Structure

A typical API request contains:

```
HTTP Method
URL
Headers
Body (optional)
```

Example request:

```
POST /users
Host: api.example.com
Content-Type: application/json

{
  "name": "Ashish",
  "email": "ashish@email.com"
}
```

---

# 4. API Response Structure

API responses typically contain:

```
Status Code
Headers
Response Body
```

Example response:

```
HTTP/1.1 200 OK
Content-Type: application/json

{
  "id": 1,
  "name": "Ashish"
}
```

---

# 5. Common HTTP Status Codes

| Code | Meaning |
|---|---|
| 200 | Success |
| 201 | Resource created |
| 400 | Bad request |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Resource not found |
| 500 | Internal server error |

Example:

```
HTTP 200 → Request successful
HTTP 404 → Resource not found
```

---

# 6. API Authentication Methods

Many APIs require authentication.

### API Key

Example:

```
https://api.example.com/data?api_key=123456
```

---

### Bearer Token (JWT)

Used in most modern APIs.

Example header:

```
Authorization: Bearer token_here
```

---

### Basic Authentication

Uses username and password.

```
Authorization: Basic base64(username:password)
```

---

# 7. Working with APIs Using curl

`curl` is a command-line tool used to make API requests.

---

### GET Request

```bash
curl https://api.example.com/users
```

---

### POST Request

```bash
curl -X POST https://api.example.com/users \
-H "Content-Type: application/json" \
-d '{"name":"Ashish"}'
```

---

### Add Authorization Header

```bash
curl -H "Authorization: Bearer token_here" \
https://api.example.com/data
```

---

# 8. Working with APIs in Python

Python developers commonly use the **requests library**.

Install requests:

```bash
pip install requests
```

---

### GET Request Example

```python
import requests

response = requests.get("https://api.example.com/users")

print(response.status_code)
print(response.json())
```

---

### POST Request Example

```python
import requests

data = {
    "name": "Ashish",
    "email": "ashish@email.com"
}

response = requests.post(
    "https://api.example.com/users",
    json=data
)

print(response.json())
```

---

# 9. Sending Headers in Python

```python
headers = {
    "Authorization": "Bearer token_here"
}

response = requests.get(
    "https://api.example.com/data",
    headers=headers
)
```

---

# 10. Handling API Errors

Always check the response status.

Example:

```python
if response.status_code == 200:
    print("Success")
else:
    print("Error:", response.status_code)
```

---

# 11. Parsing JSON Responses

Most APIs return **JSON data**.

Example response:

```json
{
  "id": 1,
  "name": "Ashish"
}
```

Access data in Python:

```python
data = response.json()
print(data["name"])
```

---

# 12. Pagination in APIs

Large APIs return results in pages.

Example request:

```
GET /users?page=1&limit=10
```

Example response:

```
{
  "page": 1,
  "total_pages": 10,
  "data": [...]
}
```

---

# 13. Rate Limiting

APIs often limit request frequency.

Example header:

```
X-RateLimit-Limit: 100
X-RateLimit-Remaining: 50
```

If exceeded:

```
HTTP 429 Too Many Requests
```

---

# 14. API Testing Tools

Developers commonly test APIs using tools such as:

| Tool | Purpose |
|---|---|
| Postman | GUI API testing |
| Insomnia | Lightweight API testing |
| curl | Command line API requests |
| Swagger UI | API documentation and testing |

---

# 15. Best Practices When Working with APIs

1. Always check response status codes
2. Handle API errors properly
3. Use environment variables for API keys
4. Implement retry logic
5. Respect API rate limits
6. Cache responses when possible

---

# Summary

Core concepts developers should know when working with APIs:

```
HTTP methods (GET, POST, PUT, DELETE)
Status codes
Authentication
Headers
JSON responses
Rate limiting
Pagination
```

Common tools:

```
curl
requests (Python)
Postman
```

Understanding APIs is essential for **building modern applications, integrating services, and working with cloud platforms**.
