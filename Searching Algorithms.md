
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

find the position of a target value within a ****sorted**** array
repeatedly dividing the search interval in half until the target value is found 
or the interval is empty. 
The search interval is halved by comparing the target element with the middle value of the search space.

- The data structure must be sorted.
- Access to any element of the data structure should take constant time.