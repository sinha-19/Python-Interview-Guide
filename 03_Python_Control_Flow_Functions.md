# 3. Control Flow and Functions

---

## Conditional Statements

```python
if x > 0:
    print("Positive")
elif x < 0:
    print("Negative")
else:
    print("Zero")
```

- Use `and`, `or`, `not` for logical operations.
- No parentheses needed for conditions; indentation is required.

---

## Loops

### For Loop

```python
for i in range(5):      # 0 to 4
    print(i)
for item in [1,2,3]:
    print(item)
```

### While Loop

```python
count = 0
while count < 3:
    print(count)
    count += 1
```

### Loop Control

- `break` — Exit the loop
- `continue` — Skip to next iteration
- `else` with loops — Runs if no break occurs

```python
for x in range(5):
    if x == 3:
        break
else:
    print("Completed without break")
```

---

## Functions

- Defined with `def` keyword.
- Can have default, positional, and keyword arguments.

```python
def greet(name, msg="Hello"):
    print(f"{msg}, {name}!")

greet("Alice")              # Hello, Alice!
greet("Bob", msg="Hi")      # Hi, Bob!
```

### Return Values

```python
def add(a, b):
    return a + b
```

### Variable Number of Arguments

```python
def foo(*args, **kwargs):
    print(args)
    print(kwargs)
foo(1, 2, three=3)
# args: (1, 2)
# kwargs: {'three': 3}
```

### Lambda Functions

- Anonymous, single-expression functions.

```python
square = lambda x: x * x
print(square(5))        # 25
```

---

## Scope and Global Variables

- Variables defined in a function are local by default.
- Use `global` to modify global variables.

```python
x = 10
def change():
    global x
    x = 20
```

---

## Common Pitfalls

- Forgetting indentation.
- Using mutable default arguments (`def foo(x=[])` — avoid this!).
- Not returning values (default is `None`).

---

## Interview Tips

- Know the difference between mutable and immutable defaults.
- Be comfortable with list/dict comprehensions.
- Understand variable scope (local, global, nonlocal).

---

## Possible Follow-Up Questions

- What is the difference between `*args` and `**kwargs`?
- How can you return multiple values from a function?
- What happens if no return statement is present?
