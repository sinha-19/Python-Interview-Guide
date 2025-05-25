# 10. Decorators and Context Managers

---

## Decorators

- **Decorator:** A function that takes another function and extends/modifies its behavior without changing its source code.

### Basic Function Decorator

```python
def my_decorator(func):
    def wrapper(*args, **kwargs):
        print("Before call")
        result = func(*args, **kwargs)
        print("After call")
        return result
    return wrapper

@my_decorator
def say_hello():
    print("Hello!")

say_hello()
# Output:
# Before call
# Hello!
# After call
```

### Chaining and Decorating Functions with Arguments

```python
def repeat(times):
    def decorator(func):
        def wrapper(*args, **kwargs):
            for _ in range(times):
                func(*args, **kwargs)
        return wrapper
    return decorator

@repeat(3)
def laugh():
    print("Ha!")
```

### Using `functools.wraps`

- Preserves metadata (name, docstring) of the original function.

```python
from functools import wraps

def my_decorator(func):
    @wraps(func)
    def wrapper(*args, **kwargs):
        # ...
        return func(*args, **kwargs)
    return wrapper
```

---

## Class Decorators

```python
def singleton(cls):
    instances = {}
    def getinstance(*args, **kwargs):
        if cls not in instances:
            instances[cls] = cls(*args, **kwargs)
        return instances[cls]
    return getinstance

@singleton
class MyClass:
    pass
```

---

## Context Managers

- Manage resources, setup and cleanup automatically.
- Most common use: file operations (`with open(...) as f:`).

### Using `with` Statement

```python
with open('file.txt') as f:
    data = f.read()
# File is automatically closed
```

### Custom Context Manager (with `__enter__` and `__exit__`)

```python
class MyContext:
    def __enter__(self):
        print("Enter!")
        return self
    def __exit__(self, exc_type, exc_val, exc_tb):
        print("Exit!")

with MyContext():
    print("Inside context")
```

### Using `contextlib` Module

```python
from contextlib import contextmanager

@contextmanager
def my_context():
    print("Enter!")
    yield
    print("Exit!")

with my_context():
    print("Inside context")
```

---

## Common Pitfalls

- Forgetting to use `@wraps` in decorators (loses metadata).
- Not handling exceptions in context managers (`__exit__` can suppress exceptions if it returns `True`).

---

## Interview Tips

- Be able to write a simple function or class decorator.
- Understand when and why to use context managers (`with`).
- Know how to create both class-based and function-based context managers.

---

## Possible Follow-Up Questions

- What is the difference between a decorator and a context manager?
- How do you pass arguments to decorators?
- What does `@wraps` do?
- When would you use a context manager?
