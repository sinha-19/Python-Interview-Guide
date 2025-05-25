# 12. Testing and Best Practices

---

## Why Test?

- Ensure code correctness, prevent regressions, document expected behavior.
- Makes refactoring and collaboration safer.

---

## Types of Tests

| Type         | Purpose/Scope                                              |
|--------------|-----------------------------------------------------------|
| Unit Test    | Test small, isolated pieces (functions, classes)          |
| Integration  | Test interactions between components                      |
| Functional   | Test features from user’s perspective (end-to-end)        |
| Regression   | Guard against previously fixed bugs returning             |

---

## Built-in Testing Tools

### `unittest` (Standard Library)

```python
import unittest

class TestMath(unittest.TestCase):
    def test_add(self):
        self.assertEqual(2 + 3, 5)

if __name__ == "__main__":
    unittest.main()
```

### `pytest` (Third-party, popular)

- Simpler syntax, powerful features, rich plugins.
- Install: `pip install pytest`

```python
def add(a, b):
    return a + b

def test_add():
    assert add(2, 3) == 5
```

Run: `pytest`

---

## Mocking and Patching

- Use `unittest.mock` or `pytest`’s fixtures to replace parts of code for testing.

```python
from unittest.mock import patch

@patch('module.func_to_mock')
def test_something(mock_func):
    mock_func.return_value = 42
    assert module.func_to_mock() == 42
```

---

## Test Discovery and Naming

- Test file names: `test_*.py`
- Test function/class names: start with `test_`
- Keep tests isolated and independent.

---

## Best Practices

- Write tests for new code and bug fixes.
- Run tests automatically (CI/CD).
- Prefer small, focused tests.
- Use fixtures for setup/teardown.
- Don’t rely on test execution order.
- Keep tests fast.

---

## Code Quality Tools

| Tool           | Purpose                |
|----------------|-----------------------|
| `flake8`       | Linting (style/errors)|
| `black`        | Auto-formatting       |
| `isort`        | Import sorting        |
| `mypy`         | Static type checking  |
| `coverage`     | Test coverage report  |

---

## Interview Tips

- Be able to write a simple unit test.
- Know benefits of automated testing.
- Understand how to use mocks and fixtures.

---

## Possible Follow-Up Questions

- How do you mock dependencies in a test?
- What is the difference between `assertEqual` and `assertTrue`?
- Why is code coverage important?
- How do you run only a single test file with pytest?
