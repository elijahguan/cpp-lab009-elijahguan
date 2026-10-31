# Heap Analysis Laboratory

## Required data structure
Students must implement a priority queue as a max-heap using a dynamic array/vector. The heap must satisfy the max-heap property:

- every parent node is greater than or equal to its children;
- the root contains the maximum value;
- the left and right child indices follow the formulas:
  - left child index = 2 * i + 1
  - right child index = 2 * i + 2
  - parent index = (i - 1) / 2

## Required operations
Students must implement and analyze:

- `push(value)`: The value is added to the end of the vector and moved up until the max-heap property is returned to its original state. This process takes O(log n) and O(1) space. With a vector implementation, the O(log n) time can occasionally become O(n) due to resizing.
- `pop()`: The root is the maximum value. It gets replaced by the last value, and then moves down until the heap property is restored, which takes O(log n) time and O(1) space.
- `top()`: Takes O(1) time and space since the algorithm returns the root and does not modify the heap in any way.
- `contains(value)`: Takes O(n) time complexity since unlike a balanced BST, heaps do not organize elements by size. Therefore, it will require a full traversal of each node in the worst case. This will still take O(n) time and O(1) space.
- `buildHeap(values)`: The algorithm builds the heap from the bottom up, which has an O(n) time complexity. Even though heapifyDown can take O(log n), most of the nodes are near the bottom and will therefore only move a short distance.
- `heapSort()`: Removes maximum and reverses results, therefore taking O(n log n) time and O(n) space for the vector that is returned. With this implementation, sorting the heap also empties it.
- `heapifyUp(index)` and `heapifyDown(index)`: Both heapifyUp and heapifyDown can move a value at most the height of the heap (h), which takes O(log n). Since these functions are recursive, the space also becomes O(log n).
- `Memory Usage`:  The heap stores n values in the vector, meaning that it will take O(n) space. The heapSort function will also make a result vector, taking up an extra O(n) space where n is the number of elements. Finding the maximum in a heap has O(1) time but finding a random value will take O(n) in the worst case. 
- `Comparisons`: Unlike the heap, a balanced BST can search, insert, and delete in O(log n) time but a skewed BST will take O(n). A sorted array can take O(log n) for search, but to account for the shifting of other elements, insertion and deletion will take O(n). Since a priority queue is an ADT that allows insertion and the removal of the highest-priority item, you can implement priority queues through heaps.
## Analysis requirements
Students should discuss the complexity of the following operations:

- insertion into a heap;
- deletion of the maximum;
- building a heap from an array;
- searching for an item in an array-backed heap;
- heap sort;
- memory usage.


## Expected complexity summary
- push: O(log n)
- pop: O(log n)
- top: O(1)
- buildHeap: O(n)
- heapSort: O(n log n)
- contains: O(n) in a standard heap



Students should also compare a heap to:

- a binary search tree;
- a sorted array;
- a priority queue abstraction.
