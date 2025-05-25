# 11. Concurrency and Parallelism (threading, multiprocessing, async)

---

## What is the Difference?

- **Concurrency:** Multiple tasks make progress, possibly switching between them (can be single or multi-core).
- **Parallelism:** Multiple tasks run simultaneously (multi-core, true hardware parallelism).

---

## The `threading` Module

- For I/O-bound tasks (networking, file I/O).
- Uses OS threads; Python's GIL prevents true parallelism for CPU-bound work.

```python
import threading

def worker():
    print("Thread running")

t = threading.Thread(target=worker)
t.start()
t.join()
```

- Thread-safe data: `Queue`, `Lock`, `RLock`, `Semaphore`, etc.

---

## The `multiprocessing` Module

- For CPU-bound tasks.
- Spawns separate processes (bypasses GIL).

```python
from multiprocessing import Process

def task():
    print("Process running")

p = Process(target=task)
p.start()
p.join()
```

- Shares data via `Queue`, `Pipe`, `Value`, `Array`.

---

## The `asyncio` Module

- For asynchronous I/O, coroutines, event-loops (Python 3.4+).
- Single-threaded, single-process but handles many I/O-bound tasks efficiently.

```python
import asyncio

async def main():
    print("Hello")
    await asyncio.sleep(1)
    print("World")

asyncio.run(main())
```

- Use `async def`, `await`, `async for`, `async with`.

---

## When to Use What?

| Problem Type | Solution              | Module            |
|--------------|-----------------------|-------------------|
| CPU-bound    | Parallelism           | `multiprocessing` |
| I/O-bound    | Concurrency           | `threading`, `asyncio` |

---

## Common Pitfalls

- GIL limits parallelism in `threading` for CPU-bound tasks.
- Shared data between processes needs serialization (e.g., `Queue`, `Pipe`).
- `asyncio` is single-threaded; blocking calls freeze event-loop.
- Deadlocks, race conditions, improper exception handling.

---

## Interview Tips

- Know the GIL and its implications.
- Be able to write simple multi-threaded, multi-process, and async code.
- Understand when to use threads, processes, or async.

---

## Possible Follow-Up Questions

- What is the GIL? How does it affect threading?
- How can you share data between processes?
- What is a coroutine? How does it differ from a thread?
- How do you prevent race conditions?
