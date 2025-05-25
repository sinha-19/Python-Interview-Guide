# 6. File I/O and Exception Handling

---

## File I/O (Input and Output)

### Opening and Closing Files

```python
f = open('data.txt', 'r')   # Open for reading
data = f.read()
f.close()
```

- Always close files! (Better: use `with` statement)

### With Statement (Context Manager)

```python
with open('data.txt', 'r') as f:
    data = f.read()
# File is automatically closed
```

### Reading Files

```python
f.read()       # Read entire file
f.readline()   # Read one line
f.readlines()  # Read all lines as list
```

### Writing Files

```python
with open('out.txt', 'w') as f:
    f.write("Hello!\n")
    f.writelines(['Line 1\n', 'Line 2\n'])
```

- `'w'`: write (overwrite), `'a'`: append, `'r'`: read

---

## Exception Handling

### Basic Syntax

```python
try:
    # code that may throw an error
    result = 10 / 0
except ZeroDivisionError as e:
    print("Cannot divide by zero:", e)
except (TypeError, ValueError):
    print("Type or value error occurred")
else:
    print("No exceptions!")
finally:
    print("This always runs")
```

- `try`: Code to attempt
- `except`: Handle specific errors
- `else`: Runs if no exception
- `finally`: Always runs (cleanup)

### Raising Exceptions

```python
def sqrt(x):
    if x < 0:
        raise ValueError("Negative value")
    return x ** 0.5
```

### Custom Exceptions

```python
class MyError(Exception):
    pass

raise MyError("Something went wrong")
```

---

## Common Pitfalls

- Not closing files (use `with`!).
- Catching broad exceptions (`except Exception:`) — be specific.
- Forgetting to handle file not found or permission errors.

---

## Interview Tips

- Be comfortable reading/writing files and handling exceptions.
- Know how to create and raise custom exceptions.
- Understand the flow of `try/except/else/finally`.

---

## Possible Follow-Up Questions

- What happens if you forget to close a file?
- How do you catch multiple exception types?
- What is the difference between `w` and `a` file modes?
- When should you use custom exceptions?
