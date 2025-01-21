
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
3. if keys is found at mid, cancel process
4. if key is smaller than mid, left is searched
5. if key is larger, search right 

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
