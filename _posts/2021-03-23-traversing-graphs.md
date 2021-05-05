---
title: "Traversing Graphs"
date: 2021-03-23
tags: [Python, Data Structures and Algorithms]
excerpt: "Obtaining information from the nodes of a graph"
---

A graph is a data structure consisting of nodes or vertices that are linked together by edges. It is a great way to organize the flow of data and there are many algorithms that can be used to traverse through them. An example of a graph can be seen in the visual representation below.

```
      1
     / \
    2   3
   / \   \
  4  5    6
```

### Depth First Search (DFS)
The DFS algorithm traverses each branch depth wise before backtracking and traversing the next branch until all the nodes have been reached. The stack data structure can be used to implement this algorithm. The function would take in two parameters, *graph* and *start*, where *graph* is a dictionary that maps each node with their children and *start* represents the start node. The stack initially contains the start node, which gets added to the set of visited nodes and its children get added to the stack as long as it's not in the list of visited notes. The child node at the top of the stack gets popped and added to the visited list where the process repeats until reaching a leaf node. At this point the algorithm backtracks to the original start node and traverses the branch of the next child. The DFS algorithm run on the tree above would output [1, 2, 4, 5, 3, 6].

```python
def dfs(graph, start):
    visited, stack = set(), [start]
    while stack:
        vertex = stack.pop()
        if vertex not in visited:
            visited.add(vertex)
            stack.extend(graph[vertex] - visited)
    return visited
```

### Breadth First Search (BFS)
The BFS algorithm traverses the graph layer by layer until all nodes have been reached. This time, a queue data structure would be suitable for implementation of this algorithm. The function would take in again take in the *graph* and *start* parameters described above with DFS. The algorithm itself uses the exact same code as DFS except with a different data structure. Based on the first in first out nature of BFS, the tree is traversed by layers as opposed traversed by branch. The BFS algorithm run on the tree above would output [1, 2, 3, 4, 5, 6].

```python
def bfs(graph, start):
    visited, queue = set(), [start]
    while queue:
        vertex = queue.pop()
        if vertex not in visited:
            visited.add(vertex)
            queue.extend(graph[vertex] - visited)
    return visited
```



