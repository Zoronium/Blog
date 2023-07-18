---
title: "Get Started with FastAPI: The Efficient Python Framework for Web Development"
seoTitle: "Get Started with FastAPI: The Efficient Python Framework for Web Deve"
seoDescription: "FastAPI -the efficient Python framework for building high-performance web apps & APIs.Our guide covers installation and usage. Enhance your next project now"
datePublished: Thu Mar 02 2023 12:41:18 GMT+0000 (Coordinated Universal Time)
cuid: cler3iazo000009jl958h6qr8
slug: get-started-with-fastapi-the-efficient-python-framework-for-web-development
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/HUJDz6CJEaM/upload/d35e2370d8481b6b77398b8c8d0f34fa.jpeg
tags: python, web-development, projects, fastapi, wemakedevs

---

Now that we've covered some of the key features and benefits of FastAPI in our previous blog, let's dive into how to get started with the framework.

How to Get Started With FastAPI

1. Installation: FastAPI can be installed using pip, the Python package manager. Simply run the following command in your terminal or command prompt:
    

```bash
pip install fastapi
pip install "uvicorn[standard]"
```

1. Create a new project: To create a new FastAPI project, you can use any text editor or integrated development environment (IDE) of your choice. Create a new file named [`main.py`](http://main.py) and add the following code to get started:
    

```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def read_root():
    return {"Hello": "World"}

@app.get("/items/{item_id}")
def read_item(item_id: int, q: str = None):
    return {"item_id": item_id, "q": q}
```

1. Run the server: To run the FastAPI server, simply run the following command in your terminal or command prompt:
    

```bash
uvicorn main:app --reload
```

This will start the FastAPI server, and you can access your API by visiting [`http://localhost:8000`](http://localhost:8000) in your web browser.

FastAPI Interactive API Documentation

One of the great things about FastAPI is its built-in, interactive API documentation. This allows you to easily see how your API is structured and test it out, without having to write any additional code.

To access the API documentation, visit [`http://localhost:8000/docs`](http://localhost:8000/docs) your web browser when the FastAPI server is running. The documentation provides a clear and intuitive interface for testing your API and exploring its functionality.

Building Your First Project with FastAPI

Now that you understand how to get started with FastAPI, let's build an easy project to get a feel for how it works.

For this project, we'll build a simple to-do list API. The API will allow you to add, read, update, and delete to-do items.

1. Define the to-do model: First, let's define the to-do model by adding the following code to your [`main.py`](http://main.py) file:
    

```python
from pydantic import BaseModel

class Todo(BaseModel):
    task: str
    is_completed: bool = False
```

1. Define the to-do list: Next, let's create a simple in-memory to-do list by adding the following code to your [`main.py`](http://main.py) file:
    

```python
todos = []
```

1. Define the endpoints: Now, let's add the endpoint functions for adding, reading, updating, and deleting to-do items. Add the following code to your [`main.py`](http://main.py) file:
    

```python
@app.post("/todos")
async def create_todo(todo: Todo):
    todos.append(todo)
    return {"message": "Todo created successfully"}

@app.get("/todos")
async def read_todos():
    return {"todos": todos}

@app.put("/todos/{todo_id}")
async def update_todo(todo_id: int, todo: Todo):
todos[todo_id] = todo
return {"message": "Todo updated successfully"}

@app.delete("/todos/{todo_id}")
async def delete_todo(todo_id: int):
todos.pop(todo_id)
return {"message": "Todo deleted successfully"}
```

1. Test the endpoints: With the endpoints defined, you can now test the functionality of your to-do list API. You can use a tool like Postman or cURL to make requests to the API and verify that it's working as expected.
    

That's it! You've now built a simple to-do list API using FastAPI. This project is just a starting point, and there's plenty of room for further exploration and improvement.

In conclusion, FastAPI is a modern and efficient Python framework for building high-performance web applications and APIs. With its built-in features, including interactive API documentation and automatic data validation, FastAPI makes it easy to build and maintain your projects. Give it a try and see how it can help improve the performance of your next project.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1675574534086/275c2085-08ee-4a82-83fc-8379d5f1a513.png align="center")

## Demo Gif

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1675574904577/93c66639-9b6a-4bbb-98f3-a77ee9a25aa4.gif align="center")