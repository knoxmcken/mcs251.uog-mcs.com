# Graphs: Exercises

### Exercises

1.  Implement an undirected graph using an adjacency matrix. Given the following edges, represent the graph as a 2D list and print the adjacency matrix:

    Edges: (0, 1), (1, 2), (2, 3), (0, 3), (2, 4)
2. Implement the same graph as in Exercise 1, but this time using an adjacency list. Represent the graph as a dictionary and print the adjacency list.
3. Write a Python function to count the number of edges in an undirected graph represented by an adjacency list. Test your function with the graph from Exercise 2.
4. Implement a Python function that takes a graph represented by an adjacency list and a node index as input and returns the degree of the node (the number of edges connected to it). Test your function with the graph from Exercise 2 and node index 2.
5.  Consider the following directed graph represented as an adjacency list:

    ```python
    graph = {
        0: [1, 3],
        1: [2],
        2: [3],
        3: [4, 5],
        4: [],
        5: [6],
        6: [4]
    }
    ```

    Modify the DFS (Depth-First Search) function provided in the notes to work with directed graphs, and find the DFS traversal starting from node 0.
