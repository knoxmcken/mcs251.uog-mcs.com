# Lecture Notes: Stacks and Queues

## Introduction

In this chapter, we will explore two essential data structures in computer programming: stacks and queues. These data structures are widely used to solve various programming problems and are a foundation for understanding more advanced data structures and algorithms. We will start by defining what a stack and a queue are, then look at their properties, operations, and real-world applications. We will also provide examples in Python to help you better understand these concepts.

## Stacks

A stack is a linear data structure that follows the Last-In-First-Out (LIFO) principle, which means that the last element added to the stack is the first one to be removed. You can visualize a stack as a collection of items in a vertical arrangement, where you can only add or remove items from the top.

### Stack Operations

There are two primary operations performed on a stack:

1. Push: Adds an element to the top of the stack.
2. Pop: Removes the top element from the stack and returns it.

Additionally, some stacks may include the following operations:

3. Peek (or Top): Retrieves the top element without removing it from the stack.
4. IsEmpty: Checks if the stack is empty.

### Example: Stack Implementation in Python

Here's a simple implementation of a stack in Python using a list:

```python
class Stack:
    def __init__(self):
        self.items = []

    def push(self, item):
        self.items.append(item)

    def pop(self):
        if not self.is_empty():
            return self.items.pop()

    def peek(self):
        if not self.is_empty():
            return self.items[-1]

    def is_empty(self):
        return len(self.items) == 0

    def size(self):
        return len(self.items)
```

### Real-world Applications of Stacks

Some practical applications of stacks include:

1. Expression evaluation and syntax parsing (e.g., checking for balanced parentheses)
2. Undo/Redo functionality in software applications
3. Call stack management in programming languages

## Queues

A queue is another linear data structure that follows the First-In-First-Out (FIFO) principle, meaning the first element added to the queue is the first one to be removed. You can visualize a queue as a line of people waiting at a bus stop, where new people join at the back and those at the front leave the queue first.

### Queue Operations

The primary operations performed on a queue are:

1. Enqueue: Adds an element to the end of the queue.
2. Dequeue: Removes the front element from the queue and returns it.

Additional operations may include:

3. Front: Retrieves the front element without removing it from the queue.
4. IsEmpty: Checks if the queue is empty.
5. Size: Returns the number of elements in the queue.

### Example: Queue Implementation in Python

Here's a simple implementation of a queue in Python using a list:

```python
class Queue:
    def __init__(self):
        self.items = []

    def enqueue(self, item):
        self.items.insert(0, item)

    def dequeue(self):
        if not self.is_empty():
            return self.items.pop()

    def front(self):
        if not self.is_empty():
            return self.items[-1]

    def is_empty(self):
        return len(self.items) == 0

    def size(self):
        return len(self.items)
```

### Real-world Applications of Queues

Some practical applications of queues include:

1. Job scheduling in operating systems
2. Managing requests in web servers
3. Handling events in event-driven programming

## Variants of Stacks and Queues

In addition to the basic stack and queue data structures, there are several common variants with specific properties and use cases. We will discuss two of these variants: the double-ended queue (deque) and the priority queue.

### Double-Ended Queue (Deque)

A double-ended queue, or deque, is a data structure that allows elements to be added or removed from both ends. This flexibility makes deques suitable for certain problems that require more than just the basic stack or queue operations.

Deque Operations:

1. AddFront: Adds an element to the front of the deque.
2. AddRear: Adds an element to the rear of the deque.
3. RemoveFront: Removes the front element from the deque and returns it.
4. RemoveRear: Removes the rear element from the deque and returns it.
5. IsEmpty: Checks if the deque is empty.
6. Size: Returns the number of elements in the deque.

### Example: Deque Implementation in Python

Here's a simple implementation of a deque in Python using a list:

```python
class Deque:
    def __init__(self):
        self.items = []

    def add_front(self, item):
        self.items.append(item)

    def add_rear(self, item):
        self.items.insert(0, item)

    def remove_front(self):
        if not self.is_empty():
            return self.items.pop()

    def remove_rear(self):
        if not self.is_empty():
            return self.items.pop(0)

    def is_empty(self):
        return len(self.items) == 0

    def size(self):
        return len(self.items)
```

### Priority Queue

A priority queue is a specialized data structure that assigns a priority to each element and returns the highest-priority element first. This is different from a regular queue, which follows the FIFO principle.

Priority Queue Operations:

1. Insert: Adds an element with a priority to the priority queue.
2. DeleteMax (or DeleteMin): Removes and returns the element with the highest (or lowest) priority.
3. PeekMax (or PeekMin): Retrieves the element with the highest (or lowest) priority without removing it.
4. IsEmpty: Checks if the priority queue is empty.
5. Size: Returns the number of elements in the priority queue.

Priority queues can be implemented using various data structures, such as lists, heaps, or balanced search trees.

Example: Priority Queue Implementation in Python

Here's a simple implementation of a priority queue in Python using a list:

```python
import heapq

class PriorityQueue:
    def __init__(self):
        self.items = []

    def insert(self, item, priority):
        heapq.heappush(self.items, (priority, item))

    def delete_max(self):
        if not self.is_empty():
            return heapq.heappop(self.items)[1]

    def peek_max(self):
        if not self.is_empty():
            return self.items[0][1]

    def is_empty(self):
        return len(self.items) == 0

    def size(self):
        return len(self.items)
```

In this example, we use Python's built-in heapq module to manage the priority queue. This module provides a binary heap implementation that is efficient for inserting and retrieving elements by priority.

## Summary

In this chapter, we discussed the fundamental concepts and operations related to stacks and queues, along with their Python implementations and real-world applications. We also looked at two common variants, deques and priority queues, which offer additional functionality.

Understanding stacks and queues is crucial for learning more advanced data structures and algorithms. As a programmer, you will encounter various problems that can be solved efficiently using stacks, queues, or their variants. Mastery of these data structures will not only help you in problem-solving but also serve as a foundation for understanding more complex data structures and algorithms

1.
