# Sorting Algorithms
## Bubble Sort
- compare adjacent elements, and swap them if they are out of order. Repeat until you don't have to make any swaps
- Time complexity
    - Best case: `O(n)` - list is sorted, no swaps have to be made
    - Worst case: <code>O(n<sup>2</sup>)</code> - list is in opposite order
    - Average case: <code>O(n<sup>2</sup>)</code>
    - slower than other <code>O(n<sup>2</sup>)</code> algorithms
- Space complexity
    - `O(1)`, can be done in-place
## Insertion Sort
- builds sorted array one item at a time, most similar to how people sort cards in their hand
- can be used to sort a list 'online', i.e. getting the list elements one at a time
- Time complexity
    - Best case: `O(n)` - list is sorted, no swaps have to be made
    - Worst case: <code>O(n<sup>2</sup>)</code> - array in reverse order, or any array where each element is the smallest or second-smallest of the elements before it
    - Average case: <code>O(n<sup>2</sup>)</code>
    - fastest of the quadratic sorting methods, and faster than `O(n log n)` algorithms for small lists
- Space complexity:
    - `O(1)`, can be done in-place
## Selection Sort
- similar to insertion sort, but instead of sorting the first `k` elements, it sorts the `k` smallest elements, by searching through the entire array for the next smallest element
- Time complexity:
    - Best case: <code>O(n<sup>2</sup>)</code> - no benefit even if the array is sorted, we still make all the passes
    - Worst case: <code>O(n<sup>2</sup>)</code>
    - Average case: <code>O(n<sup>2</sup>)</code>
- Space complexity:
    - `O(1)`, can be done in-place
## Mergesort
- divides the list into small units then 'merges' each adjacent list
- Time complexity:
    - Best case: `O(n log n)` - no benefit even if the array is sorted
    - Worst case: `O(n log n)`
    - Average case: `O(n log n)` - each merge takes `O(n)` time and we split the list in half `O(log n)` times
- Space complexity:
    - `O(n)`, can't be done in place due to the recursive nature
    - The recursion is similar to a depth first search, and since it executes sequentially for each level, it is bounded in linear time
- Can be implemented as a stable sort
## Quicksort
- selects a pivot element and partitions the other elements into subarray based on whether they are greater than or less than the pivot, and recursively sorts the subarray
- Time complexity:
    - Best case: `O(n log n)` - no benefit even if the array is sorted
    - Worst case: <code>O(n<sup>2</sup>)</code> - if the pivot is always the largest item in the subarray (can happen if you always choose the last element in a reverse sorted list)
    - Average case: `O(n log n)`
    - despite having a worse worst case runtime, it is generally faster than mergesort
    - different strategies to pick the pivot can also affect runtime, one example is finding the median to be the pivot, which adds a linear time operation but guarantees that we don't get the worst case
- Space complexity:
    - `O(log n)`
    - not stable
## Heapsort
- similar to an improved selection sort, but instead of doing a linear scan of the unsorted part, it stores it in a heap so it can easily get the next item to be placed into the sorted portion of the array
- Time complexity:
    - Best case: `O(n)` - only a very specific case where every item in the list is the same can we get linear performace
    - Worst case: `O(n log n)`
    - Average case: `O(n log n)`
- Space complexity:
    - `O(1)`, can be done in-place, including rearranging the unsorting portion to satisfy the heap property
    - not stable, due to rearranging elements in the heap
## Timsort
- sorting method used in Python built-in methods
- hybrid of merge sort and insertion sort, works by finding subsequences which are already ordered and merging those
- Time complexity:
    - Best case: `O(n)` - when the array is already sorted, we just need a linear scan to verify that it is sorted
    - Worst case: `O(n log n)` - same worst case as merge sort
    - Average case: `O(n log n)` - same as merge sort
- Space complexity:
    - `O(n)` - similar to merge sort. Careful not to get confused by the implementation in python, which can be used to sort a list in-place but still uses extra space to do so
## Radix Sort
- avoids direct comparisons of elements by using their radix, for integers it could be a significant digit, for strings it could use the first letter, etc.
- creates and distributes elements into buckets based on their radix, and repeats until all digits have been considered
- Time complexity:
    - Best case: `O(nk)`, where `k` is the length of the elements we're sorting.
    - Worst case: `O(nk)`
    - Average case: `O(nk)`: we have to iterate through the list `k` times to consider every digit/letter etc
- Space complexity:
    - `O(n + k)`
