
# Linear Search
```python
def search(arr, N, x):

    for i in range(0, N):
        if (arr[i] == x):
            return i
    return -1


# Driver Code
if __name__ == "__main__":
    arr = [2, 3, 4, 10, 40]
    x = 10
    N = len(arr)

    # Function call
    result = search(arr, N, x)
    if(result == -1):
        print("Element is not present in array")
    else:
        print("Element is present at index", result)
```

## Time Complexity:
Best Case:
	- first index. 
	- O(1)
Worst Case:
	- last index 
	- O(N) where N is the size of the list.
Average Case: O(N)

## Advantages
- Doesn't require additional memory
- Suitable for small datasets

## Disadvantages
- O(N) time complexity
- Slow for large datasets

When to use
- Unsorted Lists 
	- linear search is most commonly used to find any element in the collection.
- Small data sets
- Searching linked lists
	- find elements within the list for each node
- it's simple and easy

# Binary Search

repeatedly dividing the search interval in half until the target value is found 
or the interval is empty. 
The search interval is halved by comparing the target element with the middle value of the search space.

- The data structure must be sorted.
- Access to any element of the data structure should take constant time.

### advantages
1. faster than linear search, for large arrays
2. great at searching large datasets
### disadvantages
1. array needs to be sorted
2. requires data to be stored in contiguous memory
### algorithm
1. divide and search space into halves
	1. by finding middle index
2. compare mid with the key
3. if x is found at mid, cancel process
4. if x is smaller than mid, left is searched
5. if x is larger, search right 

```python
# It returns location of x in given array arr
def binarySearch(arr, low, high, x):

    while low <= high:

        mid = low + (high - low) // 2

        # Check if x is present at mid
        if arr[mid] == x:
            return mid

        # If x is greater, ignore left half
        elif arr[mid] < x:
            low = mid + 1

        # If x is smaller, ignore right half
        else:
            high = mid - 1

    # If we reach here, then the element
    # was not present
    return -1


# Driver Code
if __name__ == '__main__':
    arr = [2, 3, 4, 10, 40]
    x = 10

    # Function call
    result = binarySearch(arr, 0, len(arr)-1, x)
    if result != -1:
        print("Element is present at index", result)
    else:
        print("Element is not present in array")
```

`` mid = low + (high - low) // 2
NOT ``mid = (low + high) // 2
to prevent integer overflow. adding high and low could end in number too large.
#### recursive

```python
# Returns index of x in arr if present, else -1
def binarySearch(arr, low, high, x):

    # Check base case
    if high >= low:

        mid = low + (high - low) // 2

        # If element is present at the middle itself
        if arr[mid] == x:
            return mid

        # If element is smaller than mid, then it
        # can only be present in left subarray
        elif arr[mid] > x:
            return binarySearch(arr, low, mid-1, x)

        # Else the element can only be present
        # in right subarray
        else:
            return binarySearch(arr, mid + 1, high, x)

    # Element is not present in the array
    else:
        return -1


# Driver Code
if __name__ == '__main__':
    arr = [2, 3, 4, 10, 40]
    x = 10
    
    # Function call
    result = binarySearch(arr, 0, len(arr)-1, x)
    
    if result != -1:
        print("Element is present at index", result)
    else:
        print("Element is not present in array")
```

### Can binary search be applied to non-numeric data?

> Yes, binary search can be applied to non-numeric data as long as there is a defined order for the elements. For example, it can be used to search for strings in alphabetical order.

# Two-Pointer Technique


### Common Use Cases of Two-Pointer Technique:

1. **Finding pairs**: For problems like finding pairs that sum to a target value.
2. **Sorting or Partitioning**: Sorting or partitioning an array in-place with minimal space.
3. **Merging Arrays**: Merging two sorted arrays.
4. **Sliding Window**: Finding the maximum or minimum sum of subarrays with a fixed or variable length.

### Basic Approach

#### two sum
1. **Start with two pointers**:
    - One pointer (`left`) at the beginning of the array.
    - The second pointer (`right`) at the end of the array.
2. Compute current sum, sum = arr[left] + arr[right]
	- if sum == target, found
	- if sum < target, move left ptr to the right to increase the sum
	- if sum > target, move right ptr to the left to decrease the sum
```python
def two_sum(arr, target):
    left = 0
    right = len(arr) - 1
    
    while left < right:
        current_sum = arr[left] + arr[right]
        
        if current_sum == target:
            return True  # Found a pair that sums to the target
        elif current_sum < target:
            left += 1  # Increase the left pointer to get a larger sum
        else:
            right -= 1  # Decrease the right pointer to get a smaller sum
            
    return False  # No such pair found

# Example Usage
arr = [1, 3, 4, 6, 10, 15]
target = 10
print(two_sum(arr, target))  # Output: True (because 6 + 4 = 10)
```

#### reverse array
```python
def reverse_array(arr):
    left = 0
    right = len(arr) - 1
    
    while left < right:
        # Swap the elements at left and right
        arr[left], arr[right] = arr[right], arr[left]
        
        # Move the pointers towards each other
        left += 1
        right -= 1
    
    return arr

# Example Usage
arr = [1, 2, 3, 4, 5]
print(reverse_array(arr))  # Output: [5, 4, 3, 2, 1]
```

#### remove duplicates (sorted arr)l.

```python
def remove_duplicates(arr):
    if not arr:
        return 0  # Return 0 if the array is empty
    
    # Pointer `i` to store the index of the next unique element
    i = 0
    
    for j in range(1, len(arr)):
        if arr[i] != arr[j]:
            i += 1
            arr[i] = arr[j]  # Move the unique element to the next position
    
    # The length of the array without duplicates is i + 1
    return i + 1

# Example Usage
arr = [1, 1, 2, 3, 3, 4, 5, 5]
new_length = remove_duplicates(arr)
print(new_length)  # Output: 5 (because unique elements are [1, 2, 3, 4, 5])
print(arr[:new_length])  # Output: [1, 2, 3, 4, 5]

```
