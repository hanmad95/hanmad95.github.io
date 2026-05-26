---
title: Building APIs with FastAPI
date: 2025-05-10 13:45:00 +0100
categories: [Backend Development, Python]
tags: [fastapi, python, api, async, rest]
---

# Building APIs with FastAPI 🚀

FastAPI is a modern, fast web framework for building APIs with Python. It's built on top of Starlette and Pydantic, providing automatic validation, interactive documentation, and high performance.

## Why FastAPI?

- **Fast**: One of the fastest Python frameworks available
- **Easy**: Intuitive syntax with automatic API documentation
- **Robust**: Built-in data validation using Pydantic
- **Async by default**: Native support for async/await
- **Auto-documentation**: Swagger UI and ReDoc included
- **Type hints**: Full type hinting support for better IDE integration

## Installation

```bash
pip install fastapi uvicorn
```

- **FastAPI**: The web framework
- **Uvicorn**: ASGI server to run your application

## Your First API

Create `main.py`:

```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def read_root():
    return {"message": "Hello, World!"}

@app.get("/items/{item_id}")
def read_item(item_id: int, q: str = None):
    return {"item_id": item_id, "q": q}
```

Run the server:

```bash
uvicorn main:app --reload
```

Visit http://localhost:8000/docs for interactive API documentation.

## Request & Response Models

Use Pydantic models for automatic validation:

```python
from fastapi import FastAPI
from pydantic import BaseModel

app = FastAPI()

class Item(BaseModel):
    name: str
    price: float
    description: str = None
    tax: float = None

@app.post("/items/")
def create_item(item: Item):
    return item

@app.get("/items/{item_id}")
def read_item(item_id: int):
    return {"item_id": item_id}
```

FastAPI automatically validates incoming data and returns 422 Unprocessable Entity if validation fails.

## Path Parameters

```python
@app.get("/users/{user_id}")
def get_user(user_id: int):
    return {"user_id": user_id}

@app.get("/files/{file_path:path}")
def read_file(file_path: str):
    return {"file_path": file_path}
```

## Query Parameters

```python
@app.get("/search/")
def search(q: str, skip: int = 0, limit: int = 10):
    return {"query": q, "skip": skip, "limit": limit}
```

Optional parameters with defaults:

```python
@app.get("/products/")
def list_products(
    category: str = None,
    min_price: float = 0,
    max_price: float = 1000
):
    return {
        "category": category,
        "price_range": f"${min_price} - ${max_price}"
    }
```

## HTTP Methods

```python
@app.get("/items/")
def list_items():
    return []

@app.post("/items/")
def create_item(item: Item):
    return item

@app.put("/items/{item_id}")
def update_item(item_id: int, item: Item):
    return {"item_id": item_id, "item": item}

@app.delete("/items/{item_id}")
def delete_item(item_id: int):
    return {"deleted": item_id}

@app.patch("/items/{item_id}")
def patch_item(item_id: int, item: Item):
    return {"item_id": item_id, "item": item}
```

## Status Codes

```python
from fastapi import FastAPI, status

@app.post("/items/", status_code=status.HTTP_201_CREATED)
def create_item(item: Item):
    return item

@app.delete("/items/{item_id}", status_code=status.HTTP_204_NO_CONTENT)
def delete_item(item_id: int):
    pass  # Return nothing with 204
```

## Error Handling

```python
from fastapi import FastAPI, HTTPException

@app.get("/items/{item_id}")
def read_item(item_id: int):
    if item_id < 0:
        raise HTTPException(
            status_code=400,
            detail="Item ID must be positive"
        )
    if item_id > 1000:
        raise HTTPException(
            status_code=404,
            detail="Item not found"
        )
    return {"item_id": item_id}
```

## Async / Await

```python
import asyncio
from fastapi import FastAPI

app = FastAPI()

@app.get("/items/{item_id}")
async def read_item(item_id: int):
    # Perform async operations
    await asyncio.sleep(1)
    return {"item_id": item_id}

@app.get("/slow/")
async def slow_operation():
    # Simulate I/O operation
    result = await some_async_function()
    return result
```

## Dependencies

Reuse logic with dependency injection:

```python
from fastapi import Depends, FastAPI

async def get_query(q: str = None):
    return {"q": q}

@app.get("/items/")
async def read_items(commons: dict = Depends(get_query)):
    return commons
```

Complex dependencies:

```python
class UserDep:
    def __init__(self, user_id: int):
        self.user_id = user_id
    
    def get_user(self):
        return f"User {self.user_id}"

@app.get("/users/{user_id}/items/")
async def get_user_items(user: UserDep = Depends()):
    return {"user": user.get_user()}
```

## Authentication

```python
from fastapi import Depends, HTTPException, status
from fastapi.security import HTTPBearer, HTTPAuthCredentials

security = HTTPBearer()

async def verify_token(credentials: HTTPAuthCredentials = Depends(security)):
    if credentials.credentials != "valid-token":
        raise HTTPException(status_code=401, detail="Invalid token")
    return credentials.credentials

@app.get("/protected/")
async def protected_route(token: str = Depends(verify_token)):
    return {"message": "Access granted"}
```

## File Upload

```python
from fastapi import File, UploadFile

@app.post("/upload/")
async def upload_file(file: UploadFile = File(...)):
    contents = await file.read()
    return {
        "filename": file.filename,
        "size": len(contents)
    }

@app.post("/upload-multiple/")
async def upload_multiple(files: list[UploadFile] = File(...)):
    return {"count": len(files)}
```

## CORS (Cross-Origin Resource Sharing)

```python
from fastapi.middleware.cors import CORSMiddleware

app.add_middleware(
    CORSMiddleware,
    allow_origins=["https://example.com"],
    allow_credentials=True,
    allow_methods=["*"],
    allow_headers=["*"],
)
```

## Tags & Descriptions

Organize API documentation:

```python
@app.get("/users/", tags=["users"])
def list_users():
    """List all users"""
    return []

@app.get(
    "/items/{item_id}",
    tags=["items"],
    summary="Get Item",
    description="Get a specific item by ID"
)
def get_item(item_id: int):
    return {"item_id": item_id}
```

## Testing

```bash
pip install pytest httpx
```

Create `test_main.py`:

```python
from fastapi.testclient import TestClient
from main import app

client = TestClient(app)

def test_read_root():
    response = client.get("/")
    assert response.status_code == 200
    assert response.json() == {"message": "Hello, World!"}

def test_read_item():
    response = client.get("/items/42?q=test")
    assert response.status_code == 200
    assert response.json() == {"item_id": 42, "q": "test"}
```

Run tests:

```bash
pytest test_main.py -v
```

## Production Deployment

For production, use a production ASGI server:

```bash
# Using Gunicorn with Uvicorn workers
pip install gunicorn
gunicorn main:app --workers 4 --worker-class uvicorn.workers.UvicornWorker
```

## Performance Tips

- Use async functions for I/O-bound operations
- Implement caching for expensive operations
- Use background tasks for long-running operations
- Add request/response compression
- Monitor with tools like Prometheus

```python
from fastapi import BackgroundTasks

@app.post("/send-email/")
async def send_email(background_tasks: BackgroundTasks, email: str):
    background_tasks.add_task(send_email_task, email)
    return {"status": "Email scheduled"}

def send_email_task(email: str):
    # Long-running task
    pass
```

## Resources

- [FastAPI Documentation](https://fastapi.tiangolo.com/)
- [Starlette Middleware](https://www.starlette.io/middleware/)
- [Pydantic Documentation](https://docs.pydantic.dev/)
- [Uvicorn Server](https://www.uvicorn.org/)

## Conclusion

FastAPI makes it easy to build modern, high-performance APIs with Python. With automatic validation, async support, and built-in documentation, you can focus on business logic instead of boilerplate. Start building your next API with FastAPI today! 🎉
