# 7. Python Standard Library & Useful Modules

---

## Why Use the Standard Library?

- Comes with Python—no installation needed.
- Reliable, well-tested, cross-platform.

---

## Commonly Used Modules

| Module        | Purpose/Example Use                                    |
|---------------|--------------------------------------------------------|
| `os`          | OS interaction: paths, env vars, process management    |
| `sys`         | Interpreter variables, args, exit, modules             |
| `math`        | Mathematical functions: `sqrt`, `ceil`, `pi`           |
| `random`      | Random numbers, shuffling, selections                  |
| `datetime`    | Dates and times, formatting, arithmetic                |
| `time`        | Timestamps, sleep, performance                         |
| `collections` | Specialized containers: `deque`, `Counter`, `defaultdict` |
| `itertools`   | Efficient looping: `product`, `permutations`, `groupby`|
| `functools`   | Higher-order functions, `lru_cache`, `partial`         |
| `re`          | Regular expressions                                    |
| `json`        | JSON serialization/deserialization                     |
| `csv`         | Reading/writing CSV files                              |
| `subprocess`  | Run external commands/processes                        |
| `shutil`      | High-level file operations (copy, move, remove)        |
| `argparse`    | Command-line argument parsing                          |
| `logging`     | Flexible logging framework                             |
| `threading`   | Thread-based concurrency                               |
| `unittest`    | Unit testing framework                                 |

---

## Example: Using Some Modules

```python
import os
print(os.getcwd())              # Current working directory

import sys
print(sys.version)              # Python version

import math
print(math.sqrt(16))            # 4.0

import random
print(random.randint(1, 10))    # Random integer 1-10

import datetime
print(datetime.date.today())    # Current date

from collections import Counter
c = Counter("banana")
print(c)                        # Counter({'a': 3, 'b': 1, 'n': 2})
```

---

## Example: JSON and CSV

```python
import json
data = {'a': 1}
with open('data.json', 'w') as f:
    json.dump(data, f)
with open('data.json') as f:
    print(json.load(f))         # {'a': 1}

import csv
with open('data.csv', 'w', newline='') as f:
    writer = csv.writer(f)
    writer.writerow(['name', 'age'])
    writer.writerow(['Alice', 30])
```

---

## Example: `argparse` for CLI Tools

```python
import argparse
parser = argparse.ArgumentParser(description="Demo")
parser.add_argument('--num', type=int, default=0)
args = parser.parse_args()
print(args.num)
```

---

## Common Pitfalls

- Overlooking powerful standard modules (`collections`, `itertools`).
- Using `eval()` for JSON/parsing (use `json.loads()`).
- Forgetting cross-platform issues with `os.path`.

---

## Interview Tips

- Know the main modules and their purposes.
- Be able to use `json`, `csv`, `os`, `sys`, and `argparse` in simple scripts.
- Understand how to find more modules in the docs (`https://docs.python.org/3/library/`).

---

## Possible Follow-Up Questions

- How do you read/write JSON in Python?
- When should you use `defaultdict` or `Counter`?
- How do you run a shell command from Python?
- What’s the difference between `os` and `sys`?
