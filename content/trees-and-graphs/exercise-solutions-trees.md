# Exercise Solutions: Trees

Here are the solutions for the five exercises:

1. Calculate the height of a binary tree.

```python
class TreeNode:
    def __init__(self, value):
        self.value = value
        self.left = None
        self.right = None

def height(root: TreeNode) -> int:
    if root is None:
        return -1
    return 1 + max(height(root.left), height(root.right))
```

2. Search for a value in a Binary Search Tree (BST).

```python
class BSTNode(TreeNode):
    def insert(self, value):
        if value < self.value:
            if self.left is None:
                self.left = BSTNode(value)
            else:
                self.left.insert(value)
        else:
            if self.right is None:
                self.right = BSTNode(value)
            else:
                self.right.insert(value)

def search_bst(root: BSTNode, target: int) -> bool:
    if root is None:
        return False
    if target == root.value:
        return True
    elif target < root.value:
        return search_bst(root.left, target)
    else:
        return search_bst(root.right, target)
```

3. Implement an in-order tree traversal.

```python
def in_order_traversal(root: TreeNode) -> List[int]:
    if root is None:
        return []
    return in_order_traversal(root.left) + [root.value] + in_order_traversal(root.right)
```

4. Check if a given binary tree is a valid Binary Search Tree (BST).

```python
def is_bst(root: TreeNode, lower_bound=float('-inf'), upper_bound=float('inf')) -> bool:
    if root is None:
        return True
    if not lower_bound < root.value < upper_bound:
        return False
    return (is_bst(root.left, lower_bound, root.value) and
            is_bst(root.right, root.value, upper_bound))
```

5. Implement an AVL tree.

```python
class AVLNode(BSTNode):
    def __init__(self, value):
        super().__init__(value)
        self.height = 1

    def get_balance(self):
        left_height = self.left.height if self.left else 0
        right_height = self.right.height if self.right else 0
        return left_height - right_height

    def update_height(self):
        left_height = self.left.height if self.left else 0
        right_height = self.right.height if self.right else 0
        self.height = 1 + max(left_height, right_height)

    def rotate_right(self):
        new_root = self.left
        self.left = new_root.right
        new_root.right = self
        self.update_height()
        new_root.update_height()
        return new_root

    def rotate_left(self):
        new_root = self.right
        self.right = new_root.left
        new_root.left = self
        self.update_height()
        new_root.update_height()
        return new_root

class AVLTree:
    def __init__(self):
        self.root = None

    def insert(self, value):
        if self.root is None:
            self.root = AVLNode(value)
        else:
            self.root = self._insert(self.root, value)

    def _insert(self, node, value):
        if node is None:
            return AVLNode(value)

        if value < node.value:
            node.left = self._insert(node.left, value)
        else:
            node.right = self._insert(node.right, value)

        node.update_height()

        balance = node.get_balance()

        if balance > 1:  # Left-heavy
            if node.left.get_balance() < 0:
               
```
