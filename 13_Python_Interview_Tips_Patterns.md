# 13. Tips for Python Coding Interviews & Problem Solving Patterns

---

## Interview Mindset

- **Clarify requirements**: Ask questions before starting.
- **Communicate**: Explain your thought process as you code.
- **Write readable code**: Use good names, clear logic, and comments if needed.
- **Optimize last**: Make it work, then make it better if asked.

---

## Common Problem-Solving Patterns

### 1. Sliding Window

- For subarrays/substrings, max/min sum, longest/shortest window.

```python
def max_subarray_sum(nums, k):
    window_sum = sum(nums[:k])
    max_sum = window_sum
    for i in range(k, len(nums)):
        window_sum += nums[i] - nums[i-k]
        max_sum = max(max_sum, window_sum)
    return max_sum
```

---

### 2. Two Pointers

- For sorted arrays, reverse, partition, merging, removing elements.

```python
def is_palindrome(s):
    left, right = 0, len(s)-1
    while left < right:
        if s[left] != s[right]:
            return False
        left += 1; right -= 1
    return True
```

---

### 3. Hash Map / Set

- For counting, uniqueness, fast lookup.

```python
def has_duplicate(nums):
    seen = set()
    for n in nums:
        if n in seen:
            return True
        seen.add(n)
    return False
```

---

### 4. Recursion & Backtracking

- For combinations, permutations, tree/graph traversal.

```python
def factorial(n):
    if n == 0: return 1
    return n * factorial(n-1)
```

---

### 5. Stack/Queue for Traversal

- For depth-first (stack) and breadth-first (queue) search.

```python
from collections import deque
def bfs(graph, start):
    queue = deque([start])
    visited = set([start])
    while queue:
        node = queue.popleft()
        for neighbor in graph[node]:
            if neighbor not in visited:
                visited.add(neighbor)
                queue.append(neighbor)
```

---

## General Interview Tips

- Practice with LeetCode, HackerRank, CodeSignal, etc.
- Know time/space complexity basics.
- Brush up on built-in data structures (list, dict, set, tuple).
- Know Python’s useful libraries (heapq, bisect, collections, etc.).
- Understand how to write tests for your code.

---

## Tips for Writing Code in Interviews

- Use descriptive variable/function names.
- Write helper functions if logic gets complex.
- Check for edge cases (empty input, large numbers, etc.).
- If stuck, describe alternatives and trade-offs.

---

## Possible Follow-Up Questions

- How would you optimize this further?
- Can you do it in-place?
- What is the time and space complexity?
- How would you test your function?

---

## Final Checklist

- [ ] Do you fully understand the question?
- [ ] Did you consider edge cases?
- [ ] Did you use the right data structure?
- [ ] Is your code clean and readable?
- [ ] Can you explain your solution clearly?

---

**Good luck! You’ve completed the Python interview prep guide!**
