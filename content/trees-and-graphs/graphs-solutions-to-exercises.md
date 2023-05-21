# Graphs: Solutions to Exercises

1. Implement an undirected graph using an adjacency matrix.

```python
# Given edges
edges = [(0, 1), (1, 2), (2, 3), (0, 3), (2, 4)]

# Initialize an empty 5x5 adjacency matrix
adj_matrix = [[0 for _ in range(5)] for _ in range(5)]

# Fill the matrix with the given edges
for edge in edges:
    i, j = edge
    adj_matrix[i][j] = 1
    adj_matrix[j][i] = 1

# Print the adjacency matrix
for row in adj_matrix:
    print(row)
```

2. Implement the same graph as in Exercise 1, but this time using an adjacency list.

```python
# Given edges
edges = [(0, 1), (1, 2), (2, 3), (0, 3), (2, 4)]

# Initialize an empty adjacency list
adj_list = {0: [], 1: [], 2: [], 3: [], 4: []}

# Fill the adjacency list with the given edges
for edge in edges:
    i, j = edge
    adj_list[i].append(j)
    adj_list[j].append(i)

# Print the adjacency list
for node, neighbors in adj_list.items():
    print(f"{node}: {neighbors}")
```

3. Write a Python function to count the number of edges in an undirected graph represented by an adjacency list.

```python
def count_edges(graph):
    edge_count = 0
    for neighbors in graph.values():
        edge_count += len(neighbors)
    return edge_count // 2

# Test with the graph from Exercise 2
graph = {
    0: [1, 3],
    1: [0, 2],
    2: [1, 3, 4],
    3: [0, 2],
    4: [2]
}
print(count_edges(graph))  # Output: 5
```

4. Implement a Python function that returns the degree of a node in an undirected graph.

```python
def node_degree(graph, node):
    return len(graph[node])

# Test with the graph from Exercise 2 and node index 2
graph = {
    0: [1, 3],
    1: [0, 2],
    2: [1, 3, 4],
    3: [0, 2],
    4: [2]
}
print(node_degree(graph, 2))  # Output: 3
```

5. Modify the DFS function to work with directed graphs.

```python
def dfs_directed(graph, node, visited=None):
    if visited is None:
        visited = set()
        
    visited.add(node)
    print(node, end=' ')

    for neighbor in graph[node]:
        if neighbor not in visited:
            dfs_directed(graph, neighbor, visited)

# Test with the directed graph
graph = {
    0: [1, 3],
    1: [2],
    2: [3],
    3: [4, 5],
    4: [],
    5: [6],
    6: [4]
}

start_node = 0
dfs_directed(graph, start_node)  # Output: 0 1 2 3 4 5 6
```

