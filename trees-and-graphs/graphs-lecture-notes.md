# Graphs: Lecture Notes

### 7.2 Graphs

Graphs are a versatile data structure that can be used to represent relationships between different objects, nodes, or points. In a graph, objects are represented as nodes (or vertices), and the relationships between them are represented as edges. Graphs can be used to model various real-world problems, such as social networks, transportation networks, or even web pages and their links.

There are two main types of graphs:

1. Undirected Graph: In this type of graph, edges do not have a specific direction. That is, if there's an edge between nodes A and B, you can traverse from A to B and vice versa.
2. Directed Graph (Digraph): In this type of graph, edges have a direction, meaning you can only traverse from the starting node to the ending node along the direction of the edge.

Graphs can be represented using two common methods:

A. Adjacency Matrix

B. Adjacency List

#### A. Adjacency Matrix:

An adjacency matrix is a square matrix (2D array) where each cell represents the relationship between two nodes. If there's an edge between nodes i and j, the value at the cell (i, j) is set to 1 (or the weight of the edge, if the graph is weighted). If there's no edge, the value is set to 0.

Pros:

* Easy to implement and understand.
* Suitable for dense graphs where many edges exist.

Cons:

* Consumes more memory, especially for sparse graphs.
* Adding or removing nodes is more complex.

Example:

```python
# Undirected graph representation using adjacency matrix
graph = [
    [0, 1, 0, 1],
    [1, 0, 1, 0],
    [0, 1, 0, 1],
    [1, 0, 1, 0]
]

# Access edge between nodes 0 and 1
print(graph[0][1])  # Output: 1 (edge exists)
```

#### B. Adjacency List:

An adjacency list is a collection of lists (or dictionaries) where each list represents the neighbors of a node. The index of the list corresponds to the node, and the elements in the list are the adjacent nodes.

Pros:

* Consumes less memory, especially for sparse graphs.
* Easier to add or remove nodes.

Cons:

* Slightly more complex to implement.
* Slower for dense graphs where many edges exist.

Example:

```python
# Undirected graph representation using adjacency list
graph = {
    0: [1, 3],
    1: [0, 2],
    2: [1, 3],
    3: [0, 2]
}

# Access edge between nodes 0 and 1
print(1 in graph[0])  # Output: True (edge exists)
```

#### Graph Traversals:

There are two common graph traversal techniques:

1. Breadth-First Search (BFS)
2. Depth-First Search (DFS)

**1. Breadth-First Search (BFS):**

BFS explores the graph in layers, starting from the source node and moving outwards. It visits all neighbors of the current node before moving on to the next level. BFS can be implemented using a queue data structure.

Example:

```python
from collections import deque

def bfs(graph, start_node):
    visited = set()
    queue = deque([start_node])

    while queue:
        node = queue.popleft()
        if node not in visited:
            visited.add(node)
            print(node, end=' ')
            queue.extend(neighbor for neighbor in graph[node] if neighbor not in visited)

# Usage:
graph = {
0: [1, 2],
1: [0, 3],
2: [0, 3],
3: [1, 2]
}
start_node = 0
bfs(graph, start_node) # Output: 0 1 2 3
```

**2. Depth-First Search (DFS):**

DFS explores the graph by visiting a node and then recursively exploring its neighbors before backtracking. It can be implemented using recursion or an explicit stack data structure.

Example (using recursion):

```python
def dfs(graph, node, visited=None):
    if visited is None:
        visited = set()
        
    visited.add(node)
    print(node, end=' ')

    for neighbor in graph[node]:
        if neighbor not in visited:
            dfs(graph, neighbor, visited)

# Usage:
graph = {
    0: [1, 2],
    1: [0, 3],
    2: [0, 3],
    3: [1, 2]
}

start_node = 0
dfs(graph, start_node)  # Output: 0 1 3 2
```

**Example (using stack):**

```python
def dfs_iterative(graph, start_node):
    visited = set()
    stack = [start_node]

    while stack:
        node = stack.pop()
        if node not in visited:
            visited.add(node)
            print(node, end=' ')
            stack.extend(neighbor for neighbor in graph[node] if neighbor not in visited)

# Usage:
graph = {
    0: [1, 2],
    1: [0, 3],
    2: [0, 3],
    3: [1, 2]
}

start_node = 0
dfs_iterative(graph, start_node)  # Output: 0 2 3 1
```
