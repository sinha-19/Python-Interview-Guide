# 5. Modules, Packages, and Imports

---

## What is a Module?

- A **module** is any Python file (`.py`) containing code (functions, classes, variables).
- Modules help organize code into reusable components.

---

## Importing Modules

```python
import math
print(math.sqrt(16))        # 4.0

from math import pi, sin
print(pi)
print(sin(0))
```

- `import module` imports the whole module.
- `from module import name` imports a specific object.
- `as` can be used to alias modules or objects:

```python
import numpy as np
from collections import Counter as C
```

---

## Creating Your Own Module

- Save your code in a `.py` file (e.g., `mymodule.py`).
- Import it in another file:

```python
# mymodule.py
def greet(name):
    print(f"Hello, {name}!")

# another_file.py
import mymodule
mymodule.greet("Alice")
```

---

## Packages

- A **package** is a directory containing a special `__init__.py` file (can be empty), plus other modules or sub-packages.
- Structure example:
  ```
  mypackage/
      __init__.py
      module1.py
      module2.py
  ```

---

## Importing from Packages

```python
from mypackage import module1
from mypackage.module2 import some_function
```

---

## Standard Library vs. Third-Party Packages

- **Standard Library:** Comes with Python (e.g., `os`, `sys`, `math`, `datetime`).
- **Third-Party:** Must be installed (e.g., `requests`, `numpy`).

```bash
pip install requests
```

---

## The `if __name__ == "__main__":` Idiom

- Used to run code only when the file is executed directly, not when imported.

```python
def main():
    print("This is a script!")

if __name__ == "__main__":
    main()
```

---

## Relative Imports (within packages)

```python
from . import sibling_module
from ..subpackage import another_module
```
- Only work inside packages, not for top-level scripts.

---

## Common Pitfalls

- Import errors due to incorrect paths.
- Circular imports (two modules importing each other).
- Forgetting to add `__init__.py` in package directories (Python 3.3+ allows implicit namespaces, but explicit is safer).

---

## Interview Tips

- Know how to structure a small project into modules and packages.
- Be able to explain the difference between absolute and relative imports.
- Understand the role of `__init__.py`.

---

## Possible Follow-Up Questions

- What happens if `__init__.py` is missing?
- How do you avoid circular imports?
- How do you import a module from a parent directory?
