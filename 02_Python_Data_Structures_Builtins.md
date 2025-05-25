# 2. Data Structures and Built-in Types

---

## Core Built-in Data Structures

| Type   | Description                             | Example                   |
|--------|-----------------------------------------|---------------------------|
| list   | Ordered, mutable, allows duplicates     | `[1, 2, 3]`               |
| tuple  | Ordered, immutable, allows duplicates   | `(1, 2, 3)`               |
| set    | Unordered, unique elements              | `{1, 2, 3}`               |
| dict   | Key-value pairs, unordered (3.7+: ordered by insert) | `{"a": 1, "b": 2}` |

---

## Lists

- Mutable, can contain elements of different types.
- Common methods: `append()`, `extend()`, `pop()`, `remove()`, `sort()`, `reverse()`

```python
nums = [1, 2, 3]
nums.append(4)    # [1, 2, 3, 4]
nums[0] = 10      # [10, 2, 3, 4]
del nums[1]       # [10, 3, 4]
```

---

## Tuples

- Immutable, can be used as dict keys if elements are immutable.
- Tuple unpacking:  
  ```python
  a, b = (1, 2)
  ```

---

## Sets

- No duplicates, supports set operations: union (`|`), intersection (`&`), difference (`-`).
- Methods: `add()`, `remove()`, `discard()`, `pop()`

```python
s = {1, 2, 2, 3}
# s is {1, 2, 3}
```

---

## Dictionaries

- Mapping of unique keys to values.
- Methods: `get()`, `keys()`, `values()`, `items()`, `update()`, `pop()`
- Dictionary comprehension:  
  ```python
  squares = {x: x*x for x in range(5)}
  ```

---

## String as a Data Structure

- Immutable, supports slicing, methods like `split()`, `join()`, `replace()`, `find()`, `format()`.
- Slicing: `s[1:3]`, reverse: `s[::-1]`

---

## Useful Built-in Functions

| Function  | Purpose                           |
|-----------|-----------------------------------|
| `len()`   | Get length                        |
| `sum()`   | Sum elements                      |
| `max()`   | Maximum value                     |
| `min()`   | Minimum value                     |
| `sorted()`| Return sorted list (doesn't modify original) |
| `enumerate()` | Get index and value in loops  |
| `zip()`   | Combine iterables element-wise    |
| `reversed()` | Reverse an iterable            |

---

## Iteration Examples

```python
for i, val in enumerate(['a', 'b', 'c']):
    print(i, val)

for k, v in {'a': 1, 'b': 2}.items():
    print(k, v)
```

---

## Common Pitfalls

- Modifying a list while iterating over it.
- Confusing `set` and `dict` curly braces.
- Mutable default arguments in functions (use `None` as default).

---

## Interview Tips

- Know when to use each data structure.
- Be able to convert between types: `list()`, `set()`, `dict()`, etc.
- Understand list/dict/set comprehensions and generator expressions.

---

## Possible Follow-Up Questions

- How do you remove duplicates from a list?
- What is the difference between a list and a tuple?
- When should you use a set over a list?
- How do you iterate over a dictionary’s keys and values?
