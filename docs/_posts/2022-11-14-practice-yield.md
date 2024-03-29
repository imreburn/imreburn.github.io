---
layout: post
title: Practice yield keyword (Python)
katex: false
---

When the callee function is iterable, we can use the keyword `yield`, instead of `return` to create a coroutine between the caller and callee.
As an example, two `order` functions are shown below, where both output a topological order given the number of nodes and the edges.
The first is written with `return` and the second with `yield`.

With `return` keyword, a variable `topo` is a list to store the node in topological order and will be returned at the end.
Whenever a single loop of `while` finishes, the next node in topological order is appended to the `topo`.

```python
def order(n, edges):
    from collections import defaultdict, deque
    # Build Adjacency list and in-degree
    adj = defaultdict(list)
    indeg = [0 for _ in range(n)]   
    for u, v in edges:
        adj[u].append(v)
        indeg[v] += 1 # in-degree

    q = deque([u for u in range(n) if indeg[u] == 0])
    topo = []
    while len(q) != 0:
        u = q.popleft()
        for v in adj[u]:
            indeg[v] -= 1
            if indeg[v] == 0:
                q.append(v)
        topo.append(u)
        
    return topo if len(topo) == n else None # detect cycle
```

With `yield` keyword, we do not need a variable such as `topo` to accumulate results.
However, this is not a very good example of using `yield` because the program should check in the end whether a cycle exists in the graph. (no topological order exists)

```python
def _order(n, edges):
    from collections import defaultdict, deque
    # Build Adjacency list and in-degree
    adj = defaultdict(list)
    indeg = [0 for _ in range(n)]   
    for u, v in edges:
        adj[u].append(v)
        indeg[v] += 1 # in-degree

    q = deque([u for u in range(n) if indeg[u] == 0])
    while len(q) != 0:
        u = q.popleft()
        for v in adj[u]:
            indeg[v] -= 1
            if indeg[v] == 0:
                q.append(v)
        yield u

order = lambda n, edges: topo if len(topo := list(_order(n, edges))) == n else None # detect cycle
```

### Reference
- [How to Use Generators and yield in Python](https://realpython.com/introduction-to-python-generators/)