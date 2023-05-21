# Questions

## Assignment 2

### Duration: 10 days

### Due Date: 14/05/23

**Instruction**: Answer all the questions. Use the[ starter files ](starter-files/)provided.

**Part 1: Searching and Sorting Algorithms (30 marks)**

1. Linear Search (3 marks) - Implement a function `linear_search(arr, target)` that takes a list `arr` and a target value `target` as input, and returns the index of the target in the list or -1 if not found.
2. Binary Search (3 marks) - Implement a function `binary_search(arr, target)` that takes a sorted list `arr` and a target value `target` as input, and returns the index of the target in the list or -1 if not found.
3. Bubble Sort (6 marks) - Implement a function `bubble_sort(arr)` that takes a list `arr` as input and returns the sorted list in ascending order.
4. Quick Sort (8 marks) - Implement a function `quick_sort(arr)` that takes a list `arr` as input and returns the sorted list in ascending order.
5. Merge Sort (8 marks) - Implement a function `merge_sort(arr)` that takes a list `arr` as input and returns the sorted list in ascending order.
6. Time complexity analysis (2 marks) - For each of the sorting algorithms (in questions 3, 4, and 5), analyse their time complexity in the best, average, and worst cases. Provide a brief explanation of your analysis.

**Part 2: Trees (35 marks)**

1.  Binary Tree (15 marks) - Implement a `BinaryTree` class with the following methods:&#x20;

    a. `insert(self, value)` (3 marks) - Insert a new node with the given value in the tree. \
    b. `delete(self, value)` (4 marks) - Remove the node with the given value from the tree.  \
    c. `inorder_traversal(self)` (2 marks) - Return a list of the tree's nodes in in-order traversal. \
    d. `preorder_traversal(self)` (2 marks) - Return a list of the tree's nodes in pre-order traversal. \
    e. `postorder_traversal(self)` (2 marks) - Return a list of the tree's nodes in post-order traversal.
2. Binary Search Tree (12 marks) - Implement a `BinarySearchTree` class with the following methods: \
   a. `insert(self, value)` (4 marks) - Insert a new node with the given value in the tree. \
   b. `delete(self, value)` (4 marks) - Remove the node with the given value from the tree. \
   c. `search(self, value)` (4 marks) - Return the node with the given value if it exists, otherwise return None.
3. Balanced Tree (AVL or Red-Black) (8 marks) - Implement either an `AVLTree` or `RedBlackTree` class with the following methods: \
   a. `insert(self, value)` (3 marks) - Insert a new node with the given value in the tree. \
   b. `delete(self, value)` (3 marks) - Remove the node with the given value from the tree. \
   c. `search(self, value)` (2 marks) - Return the node with the given value if it exists, otherwise return None.

**Part 3: Graphs (35 marks)**

1. Graph Representations (10 marks) - Implement two classes, `AdjacencyMatrix` and `AdjacencyList`, with the following methods: \
   a. `add_edge(self, src, dest, weight)` (5 marks for each class) - Add an edge between the source node `src` and the destination node `dest` with the given weight.
2. Graph Traversals (10 marks) - For each graph representation class, implement the following methods: \
   a. `bfs(self, start)` (5 marks for each class) - Perform a Breadth-First Search traversal starting from the node `start`, and return the visited nodes in the order they were visited. \
   b. `dfs(self, start)` (5 marks for each class) - Perform a Depth-First Search traversal starting from the node `start`, and return the visited nodes in the order they were visited.
3. Shortest Path Algorithm (15 marks) - Choose one shortest path algorithm (Dijkstra's, Bellman-Ford, or Floyd-Warshall) and implement it as a method in the graph representation classes of your choice: \
   a. Implementation of the chosen algorithm (13 marks) \
   b. Explanation of the chosen algorithm (2 marks)

**Total: 100 marks**
