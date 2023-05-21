# Exercise Solutions: Stacks and Queues

## Stacks and Queues: Exercise Solutions

1. Implement a stack using two queues:

```python
class StackUsingQueues:
    def __init__(self):
        self.queue1 = []
        self.queue2 = []

    def push(self, item):
        self.queue1.insert(0, item)

    def pop(self):
        if not self.is_empty():
            while len(self.queue1) > 1:
                self.queue2.insert(0, self.queue1.pop())
            popped_item = self.queue1.pop()
            self.queue1, self.queue2 = self.queue2, self.queue1
            return popped_item

    def top(self):
        if not self.is_empty():
            return self.queue1[0]

    def is_empty(self):
        return len(self.queue1) == 0
```

2. Implement a queue using two stacks:

```python
class QueueUsingStacks:
    def __init__(self):
        self.stack1 = []
        self.stack2 = []

    def enqueue(self, item):
        self.stack1.append(item)

    def dequeue(self):
        if not self.is_empty():
            if not self.stack2:
                while self.stack1:
                    self.stack2.append(self.stack1.pop())
            return self.stack2.pop()

    def is_empty(self):
        return len(self.stack1) == 0 and len(self.stack2) == 0
```

3. Check if a given expression has balanced parentheses:

```python
def is_balanced_parentheses(expression):
    stack = []
    opening = '([{'
    closing = ')]}'

    for char in expression:
        if char in opening:
            stack.append(char)
        elif char in closing:
            if not stack:
                return False
            if closing.index(char) != opening.index(stack.pop()):
                return False
    return not stack
```

4. Implement a palindrome checker using a deque:

```python
from collections import deque

def is_palindrome(word):
    clean_word = ''.join(c.lower() for c in word if c.isalnum())
    word_deque = deque(clean_word)
    
    while len(word_deque) > 1:
        if word_deque.popleft() != word_deque.pop():
            return False

    return True
```

5. Implement a simple job scheduler using a priority queue:

```python
import heapq

class JobScheduler:
    def __init__(self):
        self.jobs = []

    def add_job(self, job, priority):
        heapq.heappush(self.jobs, (priority, job))

    def execute_next(self):
        if not self.is_empty():
            priority, job = heapq.heappop(self.jobs)
            job()
            return priority, job

    def is_empty(self):
        return len(self.jobs) == 0

# Example usage
def job1():
    print("Job 1 executed.")

def job2():
    print("Job 2 executed.")

scheduler = JobScheduler()
scheduler.add_job(job1, 2)
scheduler.add_job(job2, 1)
scheduler.execute_next()
scheduler.execute_next()
```
