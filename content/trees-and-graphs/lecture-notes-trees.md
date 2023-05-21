# Lecture Notes: Trees

## Chapter 7: Trees and Graphs

### 7.1 Trees

In this section, we will explore trees, a fundamental data structure used in computer science. We will discuss binary trees, binary search trees, and balanced trees, such as AVL and Red-Black trees.

A tree is a hierarchical data structure that consists of nodes connected by edges. The top node is called the root, and the nodes with no children are called leaves. Each node in the tree has a parent node, except for the root.

Tree Terminology:

* **Root**: The top node in the tree.
* **Parent**: The node directly connected to another node when in the direction towards the root.
* **Child**: The node directly connected to another node when moving in the direction away from the root.
* **Siblings**: Nodes with the same parent.
* **Leaf**: A node with no children.
* **Height**: The maximum level of any node in the tree.

#### 7.1.1 Binary Trees

A binary tree is a tree data structure in which each node has at most two children, usually distinguished as "left" and "right". Here's a basic implementation of a binary tree in Python:

```python
class TreeNode:
    def __init__(self, value):
        self.value = value
        self.left = None
        self.right = None
```

#### 7.1.2 Binary Search Trees (BST)

A binary search tree (BST) is a binary tree with the following properties:

* The value of each node in the left subtree is less than the node's value.
* The value of each node in the right subtree is greater than the node's value.
* Both the left and right subtrees are also binary search trees.

BSTs are useful for efficiently performing operations like search, insertion, and deletion.

```python
class BSTNode(TreeNode):  # Inherits from TreeNode
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
```

#### 7.1.3 Balanced Trees (AVL, Red-Black Trees)

In some cases, the performance of BSTs can degrade if the tree becomes unbalanced. This can occur when the tree's height becomes large, making it more like a linked list. To mitigate this issue, balanced trees, such as AVL and Red-Black trees, are used.

**AVL Tree**: An AVL tree is a self-balancing binary search tree where the difference in heights between the left and right subtrees of any node is no more than 1. This ensures that the tree remains balanced, which results in O(log N) time complexity for search, insertion, and deletion operations.

**Red-Black Tree**: A Red-Black tree is another type of self-balancing binary search tree. It has an additional "color" property for each node, which can be either red or black. The tree follows specific rules regarding node colors to ensure balance. Like AVL trees, Red-Black trees guarantee O(log N) time complexity for search, insertion, and deletion operations.

Both AVL and Red-Black trees have their own advantages and use cases. AVL trees are more strictly balanced, resulting in slightly faster search operations, while Red-Black trees typically have faster insertion and deletion operations due to fewer rotations.
