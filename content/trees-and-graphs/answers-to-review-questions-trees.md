# Answers to Review Questions: Trees

1. The main difference between a binary tree and a binary search tree is the ordering of nodes. In a binary tree, there are no specific constraints on the arrangement of nodes. In a binary search tree, the left subtree of a node contains only nodes with values less than the node's value, and the right subtree of a node contains only nodes with values greater than the node's value.
2. Tree balancing is the process of maintaining a low height in a binary search tree to ensure that operations like insertion, deletion, and search remain efficient (O(log n)). In the context of AVL and Red-Black trees, balancing is achieved by enforcing certain properties, such as height difference in AVL trees or node coloring in Red-Black trees. When these properties are violated, the tree is rebalanced using rotations and, in the case of Red-Black trees, recoloring.
3. In a binary search tree, the in-order traversal of its nodes results in a sorted sequence of values. The in-order traversal first visits the left subtree, then the current node, and finally the right subtree. This ensures that nodes are visited in ascending order of their values.
4. A Red-Black tree must maintain the following key properties to ensure balance: \
   a. Every node is either red or black. \
   b. The root node is always black. \
   c. All leaves (NULL nodes) are black. \
   d. If a node is red, both its children must be black (i.e., no two consecutive red nodes are allowed). \
   e. Every path from a node to its descendant NULL nodes must contain the same number of black nodes.
5. AVL trees and Red-Black trees both use rotations to maintain balance, but they have different balancing strategies and performance characteristics: \
   a. AVL trees maintain a strict height difference of at most 1 between the left and right subtrees of any node, leading to better search performance (O(log n)) but slightly slower insertion and deletion due to more frequent rotations. \
   b. Red-Black trees allow for a larger height difference (2 times) between subtrees, resulting in fewer rotations and faster insertion and deletion at the cost of slightly slower search performance compared to AVL trees. In practice, Red-Black trees offer better overall performance in most scenarios due to their more relaxed balancing constraints.
