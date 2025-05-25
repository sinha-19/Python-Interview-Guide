# 8. Iterators, Generators, and Comprehensions

---

## Iterators

- **Iterator:** An object representing a stream of data; implements `__iter__()` and `__next__()`.
- All collections (`list`, `dict`, etc.) are iterable.

```python
nums = [1, 2, 3]
it = iter(nums)
print(next(it))  # 1
print(next(it))  # 2
```

---

## Generators

- **Generator:** A function that yields a sequence of values using `yield`.
- More memory efficient than lists for large data.

```python
def count_up(n):
    i = 1
    while i <= n:
        yield i
        i += 1

for val in count_up(3):  # 1, 2, 3
    print(val)
```

- Generator expressions: Like list comprehensions with `()`.

```python
gen = (x*x for x in range(5))
for val in gen:
    print(val)
```

---

## List, Dict, and Set Comprehensions

- **List comprehension:** `[expression for item in iterable if condition]`
- **Dict comprehension:** `{k: v for k, v in iterable}`
- **Set comprehension:** `{expression for item in iterable}`

### Examples

```python
squares = [x*x for x in range(5)]              # [0, 1, 4, 9, 16]
even_squares = [x*x for x in range(5) if x%2==0] # [0, 4, 16]

d = {x: x*x for x in range(3)}                 # {0: 0, 1: 1, 2: 4}
s = {x for x in [1,2,2,3]}                     # {1, 2, 3}
```

---

## Custom Iterator Example

```python
class Counter:
    def __init__(self, low, high):
        self.current = low
        self.high = high
    def __iter__(self):
        return self
    def __next__(self):
        if self.current > self.high:
            raise StopIteration
        self.current += 1
        return self.current - 1

for x in Counter(1, 3):  # 1, 2, 3
    print(x)
```

---

## Common Pitfalls

- Exhausting an iterator (cannot reuse unless recreated).
- Forgetting to use `yield` in a generator.
- Confusing generator expressions with list comprehensions.

---

## Interview Tips

- Know how to write a generator for large data processing.
- Understand differences between iterator, generator, and comprehension.
- Be able to refactor loops into comprehensions.

---

## Possible Follow-Up Questions

- When would you use a generator instead of a list?
- Can you nest comprehensions?
- What happens if you call `next()` after a generator is exhausted?
