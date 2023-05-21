# 🧩 Solutions

Exercise 1: Implement Linear Search

```python
def linear_search(arr, target):
    # Iterate through the list
    for index, element in enumerate(arr):
        # Check if the current element is equal to the target element
        if element == target:
            # If found, return the index
            return index
    # If not found, return -1
    return -1

assert linear_search([3, 8, 15, 24, 42], 15) == 2
assert linear_search([3, 8, 15, 24, 42], 7) == -1
```

Exercise 2: Implement Binary Search (Iterative)

```python
def binary_search_iterative(arr, target):
    low, high = 0, len(arr) - 1

    # Continue searching while the low index is less than or equal to the high index
    while low <= high:
        # Calculate the middle index
        mid = (low + high) // 2
        mid_element = arr[mid]

        # Check if the middle element is equal to the target element
        if mid_element == target:
            # If found, return the middle index
            return mid
        # If the middle element is less than the target element, update the low index
        elif mid_element < target:
            low = mid + 1
        # If the middle element is greater than the target element, update the high index
        else:
            high = mid - 1

    # If not found, return -1
    return -1

assert binary_search_iterative([1, 5, 9, 11, 16, 22], 9) == 2
assert binary_search_iterative([1, 5, 9, 11, 16, 22], 15) == -1
```

Exercise 3: Implement Selection Sort

```python
def selection_sort(arr):
    n = len(arr)
    
    # Iterate through the list
    for i in range(n):
        # Find the index of the minimum element in the remaining unsorted sublist
        min_index = i
        for j in range(i + 1, n):
            if arr[j] < arr[min_index]:
                min_index = j
        
        # Swap the minimum element with the first unsorted element
        arr[i], arr[min_index] = arr[min_index], arr[i]

test_list = [64, 34, 25, 12, 22, 11, 90]
selection_sort(test_list)
assert test_list == [11, 12, 22, 25, 34, 64, 90]
```

Exercise 4: Implement Insertion Sort

```python
def insertion_sort(arr):
    n = len(arr)

    # Iterate through the list starting from the second element
    for i in range(1, n):
        key = arr[i]
        j = i - 1

        # Move elements of the sorted sublist that are greater than the key
        # one position ahead to make space for the key element
        while j >= 0 and arr[j] > key:
            arr[j + 1] = arr[j]
            j -= 1
        arr[j + 1] = key

test_list = [12, 11, 13, 5, 6]
insertion_sort(test_list)
assert test_list == [5, 6, 11, 12, 13]
```



Exercise 5: Compare Sorting Algorithms&#x20;

a.For a small dataset that is mostly sorted, Bubble Sort would be a suitable choice. This is because Bubble Sort has a low overhead, is easy to implement, and has a best-case time complexity of $$O(n)$$when the list is already sorted.

b. For a large dataset with no prior information about the distribution or order of elements, Quick Sort would be an appropriate choice. Quick Sort is an efficient, in-place sorting algorithm that often outperforms other sorting algorithms like Merge Sort in practice, despite having the same average-case time complexity of $$O(n \log n)$$.Quick Sort is also generally faster than Bubble Sort, which has a worst-case and average-case time complexity of $$O(n^2)$$

c. When sorting records based on multiple fields, where the relative order of equal elements is important, Merge Sort is the preferred option. Merge Sort is a stable sorting algorithm, which means it maintains the relative order of equal elements in the sorted list. This is crucial when sorting records based on multiple fields, as it ensures that the order of the records is preserved even when equal values are present in the sorting criteria. Merge Sort also has a consistent time complexity of $$O(n \log n)$$ in all cases, making it an efficient choice for various input sizes and distributions.
