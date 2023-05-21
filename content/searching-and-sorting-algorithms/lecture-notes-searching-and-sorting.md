# 📓 Lecture Notes: Searching and Sorting

## Chapter 6: Searching and Sorting Algorithms

### Introduction to Searching Algorithms

Searching algorithms are fundamental techniques used to locate a specific element or data within a dataset, such as an array or a list. Key properties to consider when evaluating searching algorithms include their time complexity, space complexity, and suitability for different data structures. Time complexity refers to the amount of time an algorithm takes to find a particular element, often expressed in "Big O" notation. Space complexity is the amount of memory an algorithm uses during the search process. Some searching algorithms are better suited for specific data structures, such as sorted or unsorted arrays, linked lists, or trees. Understanding these properties will help you choose the most appropriate searching algorithm for your particular task and dataset.on

### 6.1 Linear Search

Linear search is a simple searching algorithm that checks every element in a list or array sequentially until the target element is found or the end of the list is reached.

**Time Complexity**: $$O(n)$$



**Algorithm**:

1. Start at the first element of the list.
2. Compare the current element with the target element.
3. If the current element is equal to the target element, return its index.
4. If not, move to the next element and repeat steps 2-3.
5. If the target element is not found, return -1.

**Python Implementation**:

```python
def linear_search(arr, target):
    for index, element in enumerate(arr):
        if element == target:
            return index
    return -1
```

### 6.2 Binary Search

Binary search is an efficient searching algorithm that works on sorted lists or arrays. It repeatedly divides the list in half and compares the middle element with the target element until the target element is found or the search interval is empty.

**Time Complexity**: $$O(\log n)$$

**Algorithm**:

1. Set the low index to 0 and the high index to the length of the list minus 1.
2. While the low index is less than or equal to the high index: a. Calculate the middle index: `mid = (low + high) // 2`. b. Compare the middle element with the target element. c. If the middle element is equal to the target element, return the middle index. d. If the middle element is less than the target element, update the low index: `low = mid + 1`. e. If the middle element is greater than the target element, update the high index: `high = mid - 1`.
3. If the target element is not found, return -1.

**Python Implementation**:

```python
def binary_search(arr, target):
    low, high = 0, len(arr) - 1

    while low <= high:
        mid = (low + high) // 2
        mid_element = arr[mid]

        if mid_element == target:
            return mid
        elif mid_element < target:
            low = mid + 1
        else:
            high = mid - 1

    return -1
```

Note that the binary search algorithm assumes that the input list or array is sorted. If the input is unsorted, you may need to sort it first before using the binary search algorithm.

In the next section, we will cover three common sorting algorithms: Bubble Sort, Quick Sort, and Merge Sort. These algorithms are widely used in practice due to their simplicity, efficiency, or a combination of both.

***

### Introduction to Sorting Algorithms

Sorting algorithms are essential tools used to arrange data in a specific order, such as numerical or alphabetical. When evaluating sorting algorithms, some important properties to consider are their time complexity, space complexity, stability, and adaptability. Time complexity refers to the amount of time an algorithm takes to sort data, and is often expressed in terms of "Big O" notation. Space complexity is the amount of memory an algorithm uses during sorting. Stability is an important characteristic that ensures that equal elements maintain their original order after sorting. Lastly, adaptability refers to an algorithm's ability to perform efficiently when given partially sorted input. Understanding these properties will help you select the best sorting algorithm for a specific task or dataset.

### 2.1 Bubble Sort

Bubble Sort is a simple sorting algorithm that repeatedly steps through the list, compares adjacent elements, and swaps them if they are in the wrong order. The algorithm continues to do this until no more swaps are needed.

**Time Complexity**: $$O(n^2)$$ in the worst and average cases, $$O(n)$$ in the best case (when the list is already sorted).

**Algorithm**:

1.  For each element in the list, perform the following steps:

    a. For each adjacent pair of elements in the list, compare them.

    b. If the elements are in the wrong order, swap them.
2. Repeat step 1 until no more swaps are needed.

**Python Implementation**:

```python
def bubble_sort(arr):
    n = len(arr)
    swapped = True

    while swapped:
        swapped = False
        for i in range(1, n):
            if arr[i - 1] > arr[i]:
                arr[i - 1], arr[i] = arr[i], arr[i - 1]
                swapped = True
        n -= 1
```

***

### 2.2 Quick Sort

Quick Sort is an efficient, in-place, comparison-based sorting algorithm that works by selecting a 'pivot' element from the list and partitioning the other elements into two groups: those less than the pivot and those greater than the pivot. The algorithm then recursively sorts the two groups.

**Time Complexity**: $$O(n^2)$$ in the worst case, $$O(n \log n)$$ in the average and best cases.

**Algorithm**:

1. Choose a pivot element from the list (commonly the first, middle, or last element).
2. Partition the list into two groups: one with elements less than the pivot, and one with elements greater than the pivot.
3. Recursively apply the Quick Sort algorithm to both groups.
4. Combine the sorted groups and the pivot to obtain the final sorted list.

**Python Implementation**:

```python
def quick_sort(arr):
    if len(arr) <= 1:
        return arr

    pivot = arr[len(arr) // 2]
    left = [x for x in arr if x < pivot]
    middle = [x for x in arr if x == pivot]
    right = [x for x in arr if x > pivot]

    return quick_sort(left) + middle + quick_sort(right)
```

### 2.3 Merge Sort

Merge Sort is an efficient, stable, comparison-based sorting algorithm that works by dividing the list into two halves, recursively sorting each half, and then merging the sorted halves to produce the final sorted list.

**Time Complexity**: $$O(n \log n)$$ in the worst, average, and best cases.

**Algorithm**:

1. If the list has only one element, it is already sorted. Return the list.
2. Split the list into two halves.
3. Recursively apply the Merge Sort algorithm to both halves.
4. Merge the two sorted halves to obtain the final sorted list.

**Python Implementation**:

```python
def merge_sort(arr):
    if len(arr) <= 1:
        return arr

    mid = len(arr) // 2
    left = arr[:mid]
    right = arr[mid:]

    left = merge_sort(left)
    right = merge_sort(right)

    return merge(left, right)

def merge(left, right):
    result = []
    i = j = 0

    while i < len(left) and j < len(right):
        if left[i] < right[j]:
            result.append(left[i])
            i += 1
        else:
            result.append(right[j])
            j += 1

    result += left[i:]
    result += right[j:]

    return result
```

To use the `merge_sort` function, simply pass your list or array as an argument:

```python
unsorted_list = [34, 7, 15, 3, 11]
sorted_list = merge_sort(unsorted_list)
print(sorted_list)  # Output: [3, 7, 11, 15, 34]
```

These three sorting algorithms—Bubble Sort, Quick Sort, and Merge Sort—are widely used in practice due to various factors such as simplicity, efficiency, and stability. Bubble Sort is a simple algorithm that works well for small datasets or lists that are already partially sorted. Quick Sort is an efficient in-place sorting algorithm that is often faster in practice than other $$O(n \log n)$$algorithms like Merge Sort. Merge Sort is a stable and efficient sorting algorithm that performs consistently well for various input sizes and distributions.
