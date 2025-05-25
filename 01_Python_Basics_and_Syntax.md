# 1. Python Basics and Syntax

---

## What is Python?

- High-level, interpreted, general-purpose programming language.
- Emphasizes readability and simplicity (“batteries included”).

---

## Key Features

- Dynamically typed
- Automatic memory management (garbage collection)
- Interpreted, not compiled
- Multi-paradigm (OOP, procedural, functional)
- Extensive standard library

---

## Basic Syntax

```python
# Print statement
print("Hello, World!")

# Indentation is required to define code blocks
if 5 > 3:
    print("Five is greater than three.")

# Variables: No type declaration needed
x = 10
y = "Python"
```

---

## Data Types

| Type      | Example          |
|-----------|------------------|
| int       | `x = 5`          |
| float     | `pi = 3.14`      |
| str       | `name = "Bob"`   |
| bool      | `flag = True`    |
| list      | `nums = [1,2,3]` |
| tuple     | `t = (1,2)`      |
| set       | `s = {1,2,3}`    |
| dict      | `d = {"a": 1}`   |

---

## Comments

```python
# This is a single-line comment

"""
This is a
multi-line comment
"""
```

---

## Input and Output

```python
name = input("Enter your name: ")
print(f"Hello, {name}")
```

---

## Type Conversion

```python
x = int("42")        # str to int
y = float("3.14")    # str to float
z = str(100)         # int to str
```

---

## Common Pitfalls

- Indentation errors (spaces vs. tabs)
- Case sensitivity (`Var` vs `var`)
- Forgetting colons (`:`) after `if`, `for`, etc.

---

## Interview Tips

- Be able to write simple scripts without IDE auto-complete.
- Know the difference between Python 2 and Python 3 (use Python 3!).
- Understand the significance of indentation.

---

## Possible Follow-Up Questions

- How is Python interpreted?
- What are mutable vs. immutable types?
- What happens if you mix spaces and tabs?
