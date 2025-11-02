---
context:
  - "[[Data Oriented Design]]"
  - "[[Software Optimization]]"
---

# Lessons From Nic Barker

Lessons learned from Nic Barker, mainly about data oriented design.

See [Nic Barker - Intro to Data Oriented Design for Games](https://www.youtube.com/watch?v=WwkuAqObplU)

---

## Performance Guidelines

Rules of thumb for good performance:

1. **Efficient layout and storage**

- Use the smallest possible data type.
- Store data by locality of use.
- Don't waste the cache line.

2. **One thing at a time, many times**

- Do one task multiple times in bulk while you still have nearby data available.
- Think about functions whether they should tale one of something, or convert them into taking arrays of things.

3. **Do as much ahead of time as possible**

- Precompute as many things as possible.

4. **Parallelism**

- If you have multiple cores, use them.

## Optimization Techniques

Split data from logic.

Remove function calls from iterations.

Hoist invariants out of loops.

Store arrays of data instead of arrays of poitners to data.

Struct fields should be ordered from largest to smallest.

Avoid using strings unless maybe a human is going to read them.

Instead of using conditional branching for boolean state, try to use data in which all members are implied to be of the same state.

Make small optimizations here and there to avoid exponential slowdowns over time.
