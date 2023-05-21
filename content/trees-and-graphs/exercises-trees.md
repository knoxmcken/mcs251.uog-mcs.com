# Exercises: Trees

### Exercises

1. Implement a function to calculate the height of a binary tree.

Given a `TreeNode` object representing the root of a binary tree, write a function `height(root: TreeNode) -> int` that returns the height of the tree. The height of a tree is defined as the number of edges in the longest path from the root to a leaf.

2. Implement a function to search for a value in a Binary Search Tree (BST).

Given a `BSTNode` object representing the root of a binary search tree and a target value, write a function `search_bst(root: BSTNode, target: int) -> bool` that returns `True` if the target value exists in the BST, and `False` otherwise.

3. Implement an in-order tree traversal.

Given a `TreeNode` object representing the root of a binary tree, write a function `in_order_traversal(root: TreeNode) -> List[int]` that returns a list of the node values in in-order traversal. In-order traversal visits the left subtree, the root, and then the right subtree.

4. Implement a function to check if a given binary tree is a valid Binary Search Tree (BST).

Given a `TreeNode` object representing the root of a binary tree, write a function `is_bst(root: TreeNode) -> bool` that returns `True` if the binary tree is a valid BST, and `False` otherwise.

5. Implement an AVL tree with the following methods:

* `insert`: Given a value, insert a new node with the value into the AVL tree.
* `delete`: Given a value, remove the node with the value from the AVL tree.
* `search`: Given a value, return `True` if the value exists in the AVL tree, and `False` otherwise.

Create a class `AVLTree` to represent the AVL tree, and implement the methods described above. You'll need to use rotations (left rotation, right rotation, left-right rotation, and right-left rotation) to maintain the balance of the tree after insertions and deletions.
