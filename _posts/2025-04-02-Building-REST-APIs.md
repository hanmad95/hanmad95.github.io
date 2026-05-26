---
title: Building Robust REST APIs
date: 2025-04-02 11:15:00 +0100
categories: [Backend Development, APIs]
tags: [rest-api, backend, design, best-practices]
---

# Building Robust REST APIs 🔌

REST APIs are the backbone of modern web applications. Let's explore how to design and build APIs that are scalable, maintainable, and easy to use.

## REST Principles

REST (Representational State Transfer) is built on these core principles:

1. **Client-Server Architecture**: Client and server are independent
2. **Stateless**: Each request contains all needed information
3. **Uniform Interface**: Consistent API design
4. **Resource-Based**: Everything is a resource (users, posts, etc.)
5. **HTTP Methods**: Use GET, POST, PUT, DELETE appropriately

## HTTP Methods

```
GET     → Retrieve resource(s)
POST    → Create new resource
PUT     → Replace entire resource
PATCH   → Update part of resource
DELETE  → Remove resource
```

## Endpoint Design

```
❌ Bad
/get_users
/create_post
/update_comment
/delete_item

✅ Good
GET    /users           → Get all users
POST   /users           → Create user
GET    /users/:id       → Get specific user
PUT    /users/:id       → Update user
DELETE /users/:id       → Delete user

GET    /users/:id/posts → Get user's posts
POST   /users/:id/posts → Create post for user
```

## Request/Response Structure

### Successful Response
```json
{
  "status": "success",
  "code": 200,
  "data": {
    "id": 1,
    "name": "John Doe",
    "email": "john@example.com"
  }
}
```

### Error Response
```json
{
  "status": "error",
  "code": 400,
  "message": "Invalid email format",
  "errors": {
    "email": ["Email is required", "Invalid format"]
  }
}
```

## Status Codes

- `200`: OK - Request successful
- `201`: Created - New resource created
- `204`: No Content - Successful, no response body
- `400`: Bad Request - Invalid input
- `401`: Unauthorized - Authentication required
- `403`: Forbidden - Authenticated but no permission
- `404`: Not Found - Resource doesn't exist
- `500`: Internal Server Error - Server error

## Versioning

Provide API versions for backward compatibility:

```
/api/v1/users
/api/v2/users
```

Include version in header:
```
GET /api/users
Accept: application/vnd.myapi.v1+json
```

## Authentication

Use industry-standard methods:

```
# API Keys (simple projects)
Authorization: Bearer YOUR_API_KEY

# JWT Tokens (recommended)
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...

# OAuth 2.0 (third-party apps)
```

## Pagination

For large datasets, implement pagination:

```
GET /users?page=1&limit=10&sort=name&order=asc

Response:
{
  "data": [...],
  "pagination": {
    "page": 1,
    "limit": 10,
    "total": 150,
    "pages": 15
  }
}
```

## Filtering & Searching

```
GET /users?status=active&role=admin
GET /posts?search=javascript&category=tutorial
GET /products?min_price=10&max_price=100
```

## Rate Limiting

Protect your API:

``` text
X-RateLimit-Limit: 1000
X-RateLimit-Remaining: 999
X-RateLimit-Reset: 1234567890
```

## CORS (Cross-Origin Resource Sharing)

Allow legitimate cross-origin requests:

``` text
Access-Control-Allow-Origin: https://example.com
Access-Control-Allow-Methods: GET, POST, PUT, DELETE
Access-Control-Allow-Headers: Content-Type, Authorization
```

## Documentation

Always provide clear documentation:

```markdown
# Users API

## Get All Users
- **Endpoint**: GET /api/v1/users
- **Auth**: Required (Bearer token)
- **Parameters**:
  - page (optional, default: 1)
  - limit (optional, default: 10)
- **Response**: 200 OK
  ```json
  {
    "data": [...]
  }
    ```
```

Use tools like Swagger/OpenAPI for interactive documentation.

## Example: Simple Node.js API

```javascript
const express = require('express');
const app = express();

app.use(express.json());

// Error handling middleware
app.use((err, req, res, next) => {
  res.status(err.status || 500).json({
    status: 'error',
    message: err.message
  });
});

app.listen(3000, () => {
  console.log('API listening on port 3000');
});
```

## Best Practices Summary

✅ Use meaningful, consistent endpoint names  
✅ Return appropriate status codes  
✅ Use standard request/response format  
✅ Implement proper authentication  
✅ Document your API thoroughly  
✅ Add rate limiting  
✅ Handle errors gracefully  
✅ Use HTTPS always  
✅ Version your API  
✅ Log important events  

Build APIs that developers love to use! 🚀
