# 🖥 Exercises

Exercise 1: Implement Linear Search

Given a list of integers and a target integer, write a Python function to implement the linear search algorithm. The function should return the index of the target integer in the list if found; otherwise, it should return -1.

```python
def linear_search(arr, target):
    # Your implementation here

assert linear_search([3, 8, 15, 24, 42], 15) == 2
assert linear_search([3, 8, 15, 24, 42], 7) == -1
```

Exercise 2: Implement Binary Search (Iterative)

Write an iterative version of the binary search algorithm. Given a sorted list of integers and a target integer, the function should return the index of the target integer in the list if found; otherwise, it should return -1.

```python
def binary_search_iterative(arr, target):
    # Your implementation here

assert binary_search_iterative([1, 5, 9, 11, 16, 22], 9) == 2
assert binary_search_iterative([1, 5, 9, 11, 16, 22], 15) == -1
```

Exercise 3: Implement Selection Sort

Given a list of integers, write a Python function to implement the selection sort algorithm. The function should sort the input list in ascending order.

```python
def selection_sort(arr):
    # Your implementation here

test_list = [64, 34, 25, 12, 22, 11, 90]
selection_sort(test_list)
assert test_list == [11, 12, 22, 25, 34, 64, 90]
```

Exercise 4: Implement Insertion Sort

Given a list of integers, write a Python function to implement the insertion sort algorithm. The function should sort the input list in ascending order.

```python
def insertion_sort(arr):
    # Your implementation here

test_list = [12, 11, 13, 5, 6]
insertion_sort(test_list)
assert test_list == [5, 6, 11, 12, 13]
```

Exercise 5: Compare Sorting Algorithms

Compare the three sorting algorithms discussed in the notes (Bubble Sort, Quick Sort, and Merge Sort) in terms of their time complexity, space complexity, and stability. Explain which algorithm you would choose for each of the following scenarios and why:

a. A small dataset that is mostly sorted.&#x20;

b. A large dataset with no prior information about the distribution or order of elements.

c. Sorting records based on multiple fields, where the relative order of equal elements is important.
