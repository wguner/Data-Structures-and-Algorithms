|   Data Structure   | Insertion |                         Removal                          |                 Searching                 | Access |
| :----------------: | :-------: | :------------------------------------------------------: | :---------------------------------------: | :----: |
| Singly Linked List |   O(1)    | bestCase(very beginning): O(1) worstCase(very end): O(n) |                   O(n)                    |  O(n)  |
| Doubly Linked List |   O(1)    |                           O(1)                           | O(n) it is faster than Singly Linked List |  O(n)  |
|       Stack        |   O(1)    |                           O(1)                           |                   O(n)                    |  O(n)  |
|       Queue        |   O(1)    |                           O(1)                           |                   O(n)                    |  O(n)  |
| Binary Search Tree | O( Log n) |                            -                             |                 O(Log n)                  |   -    |
|    Binary Heap     | O( Log n) |                        O( Log n)                         |                  O( n )                   |   -    |
|    Hash Tables     |  O( 1 )   |                          O( 1 )                          |                     -                     | O( 1 ) |

# Array

linear data structure where elements are allocated ***contiguous memory****, allowing for **constant-time access***

### Time Complexity:

| Operation             | ==Best Case== | Average Case | Worst Case |
| --------------------- | ------------- | ------------ | ---------- |
| ****Traversal****     | θ(N)          | θ(N)         | θ((N)      |
| ****Insertion****     | θ((1)         | θ(N)         | θ(N)       |
| ****Deletion****      | θ(1)          | θ(N)         | θ(N)       |
| ****==Searching==**** | θ(1)          | θ(N)         | θ(N)       |

### Auxiliary Space

|Operation|Best Case|Average Case|Worst Case|
|---|---|---|---|
|****Traversal****|θ(1)|θ(1)|θ(1)|
|****Insertion****|θ(1)|θ(N)|θ(N)|
|****Deletion****|θ(1)|θ(N)|θ(N)|
|****Searching****|θ(1)|θ(1)|θ(1)|

#### advantages
- Efficient and Fast Access
- Memory Efficiency:
	- stored in contiguous memory, reduces memory fragmentation
**Random Access** : i-th item can be accessed in O(1) Time as we have the base address and every item or reference is of same size.  

#### disadvantages
not useful in places where we have operations like insert in the middle, delete from middle and search in a ==unsorted== data.
- fixed in size
- memory allocation issues
	- can cause memory exhaustion in systems with limited resources
- insertion and deleting
	- requires shifting so its inefficient
- can store on type of data type

## Operations

#### 1. Array Traversal:

Array traversal involves visiting all the elements of the array once.

```python
# This list will store integer type elements 
arr = [1, 2, 3, 4, 5]  # Traversing over arr 
for i in range(len(arr)):     
	print(arr[i], end=" ")   
```

### 2. Insertion

```python
# Example usage 
arr = [1, 2, 3, 4, 5] 
x = 10   # Element to be inserted 
pos = 2  # Position to insert the element  
arr.insert(pos, x)  
# Print the updated list 
print("Updated List:", arr)  
```

### 3. Deletion

``` python 
# Initialize a list
arr = [10, 20, 30, 40, 50]

# Value to delete
key = 40

# Remove the element with the specified value
# if present in the list
if key in arr:
   arr.remove(key)
else:
   print("Element Not Found")

# Output the modified list
print(arr)  # Output: [10, 20, 30, 50]

```

### 4. Searching

``` python
# Function to implement search operation
def find_element(arr, n, key):
    for i in range(n):
        if arr[i] == key:
            return i
    return -1

```

### Time Complexity:

|Operation|Best Case|Average Case|Worst Case|
|---|---|---|---|
|****Traversal****|θ(N)|θ(N)|θ((N)|
|****Insertion****|θ((1)|θ(N)|θ(N)|
|****Deletion****|θ(1)|θ(N)|θ(N)|
|****Searching****|θ(1)|θ(N)|θ(N)|

### Auxiliary Space

|Operation|Best Case|Average Case|Worst Case|
|---|---|---|---|
|****Traversal****|θ(1)|θ(1)|θ(1)|
|****Insertion****|θ(1)|θ(N)|θ(N)|
|****Deletion****|θ(1)|θ(N)|θ(N)|
|****Searching****|θ(1)|θ(1)|θ(1)|
