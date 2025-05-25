# 9. Functional Programming Tools (map, filter, functools, etc.)

---

## Functional Programming in Python

- Treat functions as first-class objects (pass as arguments, return from functions).
- Emphasizes immutability and no side effects (not strictly enforced in Python).

---

## map(), filter(), reduce()

### map(function, iterable, ...)

- Applies a function to every item in an iterable.

```python
nums = [1, 2, 3]
squared = list(map(lambda x: x*x, nums))   # [1, 4, 9]
```

### filter(function, iterable)

- Filters items for which the function returns `True`.

```python
nums = [1, 2, 3, 4]
even = list(filter(lambda x: x % 2 == 0, nums))   # [2, 4]
```

### reduce(function, iterable[, initializer])

- Applies a rolling computation to sequential pairs.
- Import from `functools`.

```python
from functools import reduce
total = reduce(lambda x, y: x + y, [1, 2, 3, 4])   # 10
```

---

## lambda Functions

- Anonymous, short functions.

```python
add = lambda a, b: a + b
print(add(2, 3))    # 5
```

---

## Built-in Higher-Order Functions

- `sorted(iterable, key=func)`: Sorts using a custom key function.
- `any(iterable)`, `all(iterable)`: Check if any/all elements are True.

```python
words = ['apple', 'banana', 'cherry']
print(sorted(words, key=lambda x: len(x)))  # ['apple', 'banana', 'cherry']
```

---

## functools Module

| Function        | Purpose                                      |
|-----------------|----------------------------------------------|
| `reduce()`      | Rolling computation (see above)              |
| `partial()`     | Fix some function args, return new function  |
| `lru_cache()`   | Memoize results of expensive function calls  |
| `wraps()`       | Preserve metadata when decorating functions  |

```python
from functools import partial, lru_cache

# partial example
def power(base, exp):
    return base ** exp
square = partial(power, exp=2)
print(square(5))    # 25

# lru_cache example
@lru_cache(maxsize=32)
def fib(n):
    if n < 2:
        return n
    return fib(n-1) + fib(n-2)
```

---

## Comprehensions vs. map/filter

- Comprehensions are usually clearer and more Pythonic:

```python
squared = [x*x for x in nums]
even = [x for x in nums if x % 2 == 0]
```

---

## Common Pitfalls

- Forgetting to convert `map`/`filter`/`zip` objects to list in Python 3.
- Overusing lambdas—can reduce code readability.
- Using side effects inside lambdas (avoid!).

---

## Interview Tips

- Know when and why to use functional tools.
- Be able to implement simple decorators.
- Understand the difference between `map/filter` and comprehensions.

---

## Possible Follow-Up Questions

- When would you use `reduce` instead of a for-loop?
- What is a closure? How are they used in Python?
- How does `lru_cache` work?
