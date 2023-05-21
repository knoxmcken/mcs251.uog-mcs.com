# Heaps

**8.1 Introduction to Heaps**

A **Heap** is a special type of binary tree where every parent node is either less than or equal to (Min-Heap) or greater than or equal to (Max-Heap) its child node(s). The most significant property of a heap is that it always maintains its status as a heap during insertions and deletions, and it is also complete, meaning all levels of the tree are fully filled except for the last level, which is filled from left to right.

Max-Heap:

$$
\forall n, a[n] \geq a[2n+1] \quad and \quad a[n] \geq a[2n+2]
$$

Min-Heap:

$$
\forall n, a[n] \leq a[2n+1] \quad and \quad a[n] \leq a[2n+2]
$$

**8.2 Understanding the Heap Property**

The Heap data structure obeys a certain set of rules, known as Heap Property:

* Max Heap Property: For every node i, the value of i is **less than or equal to** its parent value. This property should be true for every node in the binary tree, except the root node.

$$
\forall i > 0, \; a[\lfloor i/2 \rfloor] \geq a[i]
$$

* Min Heap Property: For every node i, the value of i is **greater than or equal to** its parent value. This property should be true for every node in the binary tree, except the root node.

$$
\forall i > 0, \; a[\lfloor i/2 \rfloor] \leq a[i]
$$

**8.3 Implementing a Heap in Python**

Here is a simple Python implementation of a Max Heap:

```python
import sys

class MaxHeap:

    def __init__(self, maxsize):
        self.maxsize = maxsize
        self.size = 0
        self.Heap = [0]*(self.maxsize + 1)
        self.Heap[0] = sys.maxsize
        self.FRONT = 1

    # Function to return the position of parent for the node currently at position 'i'
    def parent(self, i):
        return i//2

    # Function to insert a node into the heap
    def insert(self, element):
        if self.size >= self.maxsize :
            return
        self.size+= 1
        self.Heap[self.size] = element

        current = self.size

        while self.Heap[current] > self.Heap[self.parent(current)]:
            self.swap(current, self.parent(current))
            current = self.parent(current)

    # Function to print the contents of the heap
    def Print(self):
        for i in range(1, (self.size//2)+1):
            print(" PARENT : "+ str(self.Heap[i])+" LEFT CHILD : "+
                                str(self.Heap[2 * i])+" RIGHT CHILD : "+
                                str(self.Heap[2 * i + 1]))

    # Function to swap two nodes of the heap
    def swap(self, i ,j):
        self.Heap[i], self.Heap[j] = self.Heap[j], self.Heap[i]

    # Function to heapify the node at position 'i'
    def maxHeapify(self, i):
        # ...
        # ...
        # implementation of maxHeapify goes here
```

**8.4 Basic Heap Operations**

In this section, we will look at the main operations that we can perform on a Heap data structure. These include:

* **Insertion:** In a Heap, all new elements should be inserted at the next available position from left to right. After insertion, we need to ensure that the Heap property is not violated. This is done by comparing the inserted element with its parent and moving the inserted node up the heap until it is in the correct position.
* **Deletion:** In a Heap, the deletion operation is performed at the root and replaces it with the last node in the Heap. The Heap property might be violated and needs to be maintained by moving the swapped node down the heap until it is in the correct position.
* **Heapify:** This operation is used to maintain the Heap property. This is usually called after the deletion operation. This operation is performed recursively until the Heap property is maintained.

**8.5 Heap Sort**

Heap Sort algorithm uses Binary Heap to sort an array. The steps are:

1. Build a max heap from the input data.
2. Swap the root element with the last element in the heap (the maximum element is now at the end of the heap).
3. Reduce the heap size by 1 (remove the last element from the heap).
4. Heapify the root of the now smaller heap.
5. Repeat steps 2-4 while the size of the heap is greater than 1.

Here is a Python implementation of Heap Sort:

```python
def heapify(arr, n, i):
    largest = i 
    l = 2 * i + 1
    r = 2 * i + 2 

    if l < n and arr[largest] < arr[l]:
        largest = l

    if r < n and arr[largest] < arr[r]:
        largest = r

    if largest != i:
        arr[i], arr[largest] = arr[largest], arr[i] 
        heapify(arr, n, largest)

def heapSort(arr):
    n = len(arr)

    for i in range(n//2 - 1, -1, -1):
        heapify(arr, n, i)

    for i in range(n-1, 0, -1):
        arr[i], arr[0] = arr[0], arr[i]
        heapify(arr, i, 0)

arr = [12, 11, 13, 5, 6, 7]
heapSort(arr)
print("Sorted array is", arr)
```

**Review Questions**

1. What is a Heap?
2. What are Max-Heap and Min-Heap?
3. What is the significance of a Heap being a complete binary tree?
4. What is the Heap Property?
5. How does Insertion operation work in a Heap?
6. Explain the Heapify operation.
7. How does Heap Sort work?

**Answers:**

1. A Heap is a special tree-based data structure that satisfies the heap property.
2. In a Max-Heap, for any given node I, the value of I is greater than or equal to the values of its children. In a Min-Heap, the value of I is less than or equal to the values of its children.
3. Heap being a complete binary tree is significant for several reasons. It optimizes memory use and ensures efficient, predictable operations, like insertion and deletion, that perform in $O(\log n)$ time. This structure also simplifies implementation, especially when using arrays, and is crucial for applications like priority queues and certain algorithms. In essence, it enhances the heap's efficiency and usability in many algorithmic contexts.
4. Heap property ensures that every parent node is either less than or equal to (Min-Heap) or greater than or equal to (Max-Heap) its child node(s).
5. In Heap, new elements should be inserted at the next available position from left to right. After insertion, the heap property is maintained by comparing the inserted element with its parent and moving the inserted node up the heap until it is in the correct position.
6. Heapify is an operation to maintain the Heap property. It is usually called after deletion. The operation is performed recursively until the Heap property is maintained.
7. Heap Sort works by building a max heap from the input data, then repeatedly swaps the root element with the last element in the heap, reduces the heap size by 1 (removing the last element from the heap), and finally heapifies the root of the now smaller heap. The steps are repeated while the size of the heap is greater than 1.

**Exercises**

1. Implement a Min-Heap in Python.
2. Write a function to delete a specific element from a Heap.
3. Modify the Heap Sort algorithm to work on a Min-Heap.

**Answers:**


1. Implement a Min-Heap in Python.



Here's the Python implementation for a Min-Heap:

```python
import sys

class MinHeap:

    def __init__(self, maxsize):
        self.maxsize = maxsize
        self.size = 0
        self.Heap = [0]*(self.maxsize + 1)
        self.Heap[0] = -1 * sys.maxsize
        self.FRONT = 1

    def parent(self, i):
        return i//2

    def leftChild(self, i):
        return 2 * i 

    def rightChild(self, i):
        return (2 * i) + 1

    def isLeaf(self, i):
        if i >= (self.size//2) and i <= self.size:
            return True
        return False

    def swap(self, i, j):
        self.Heap[i], self.Heap[j] = self.Heap[j], self.Heap[i]

    def minHeapify(self, i):
        if not self.isLeaf(i):
            if (self.Heap[i] > self.Heap[self.leftChild(i)] or
               self.Heap[i] > self.Heap[self.rightChild(i)]):

                if self.Heap[self.leftChild(i)] < self.Heap[self.rightChild(i)]:
                    self.swap(i, self.leftChild(i))
                    self.minHeapify(self.leftChild(i))

                else:
                    self.swap(i, self.rightChild(i))
                    self.minHeapify(self.rightChild(i))

    def insert(self, element):
        if self.size >= self.maxsize :
            return
        self.size += 1
        self.Heap[self.size] = element

        current = self.size

        while self.Heap[current] < self.Heap[self.parent(current)]:
            self.swap(current, self.parent(current))
            current = self.parent(current)

    def minHeap(self):
        for i in range(self.size//2, 0, -1):
            self.minHeapify(i)
```

2. Write a function to delete a specific element from a Heap.



Deleting a specific element from a Heap can be a bit tricky as it's not a standard operation. The following function allows you to delete an element from a Max-Heap. The function works by replacing the element to be deleted with the maximum possible value (in Python, that's `sys.maxsize`), and then calling the `heapify` function at that index. Finally, it calls the `extractMax` function to remove the max element (which is the element to be deleted) from the heap.

```python
def deleteNode(heap, num):
    toDelete = -1
    for i in range(len(heap)):
        if heap[i] == num:
            toDelete = i
            break

    if toDelete == -1:
        return heap

    heap[toDelete] = sys.maxsize
    maxHeapify(heap, toDelete)
    extractMax(heap)

    return heap
```

3. Modify the Heap Sort algorithm to work on a Min-Heap.



A Min-Heap based Heap Sort would sort the array in descending order. The steps remain the same except that we build a Min-Heap in the first step instead of a Max-Heap. Here's the implementation:

```python
def minHeapify(arr, n, i):
    smallest = i 
    l = 2 * i + 1
    r = 2 * i + 2 

    if l < n and arr[smallest] > arr

[l]:
        smallest = l

    if r < n and arr[smallest] > arr[r]:
        smallest = r

    if smallest != i:
        arr[i], arr[smallest] = arr[smallest], arr[i] 
        minHeapify(arr, n, smallest)

def heapSort(arr):
    n = len(arr)

    for i in range(n//2 - 1, -1, -1):
        minHeapify(arr, n, i)

    for i in range(n-1, 0, -1):
        arr[i], arr[0] = arr[0], arr[i]
        minHeapify(arr, i, 0)

arr = [12, 11, 13, 5, 6, 7]
heapSort(arr)
print("Sorted array is", arr)
```
