[[Backend]], [[Data Structures]]

## Search
### Binary search
an efficient algorithm for finding an item from a sorted list of items. It works by repeatedly dividing in half the portion of the list that could contain the item, until you've narrowed down the possible locations to just one
Ex. Find a word in a dictionary

```
# python
# Iterative Binary Search Function
# It returns index of x in given array arr if present,
# else returns -1
def binary_search(arr, x):
	low = 0
	high = len(arr) - 1
	mid = 0

	while low <= high:

		mid = (high + low) // 2

		# If x is greater, ignore left half
		if arr[mid] < x:
			low = mid + 1

		# If x is smaller, ignore right half
		elif arr[mid] > x:
			high = mid - 1

		# means x is present at mid
		else:
			return mid

	# If we reach here, then the element was not present
	return -1


# Test array
arr = [ 2, 3, 4, 10, 40 ]
x = 10

# Function call
result = binary_search(arr, x)

if result != -1:
	print("Element is present at index", str(result))
else:
	print("Element is not present in array")

```

```
// cpp
// C++ program to implement recursive Binary Search
#include <bits/stdc++.h>
using namespace std;
 
// A recursive binary search function. It returns
// location of x in given array arr[l..r] is present,
// otherwise -1
int binarySearch(int arr[], int l, int r, int x)
{
    if (r >= l) {
        int mid = l + (r - l) / 2;
 
        // If the element is present at the middle
        // itself
        if (arr[mid] == x)
            return mid;
 
        // If element is smaller than mid, then
        // it can only be present in left subarray
        if (arr[mid] > x)
            return binarySearch(arr, l, mid - 1, x);
 
        // Else the element can only be present
        // in right subarray
        return binarySearch(arr, mid + 1, r, x);
    }
 
    // We reach here when element is not
    // present in array
    return -1;
}
 
int main(void)
{
    int arr[] = { 2, 3, 4, 10, 40 };
    int x = 10;
    int n = sizeof(arr) / sizeof(arr[0]);
    int result = binarySearch(arr, 0, n - 1, x);
    (result == -1)
        ? cout << "Element is not present in array"
        : cout << "Element is present at index " << result;
    return 0;
}
```

### Breadth-first search

## Sorting

Merge Sort - an example of the divide and conquer strategy, array is initially divided into two equal halves and then they are combined in a sorted manner

Insertion Sort - a sorting algorithm that places an unsorted element at its suitable place in each iteration

Selection sort

Heap Sort - a comparison-based sorting technique based on Binary Heap data structure. It is similar to the selection sort where we first find the minimum element and place the minimum element at the beginning. Repeat the same process for the remaining elements.

Time complexity - O(nlogn)

## Dynamic programming 
= recursion + memoization
>simplifying a complicated problem by breaking it down into simpler sub-problems in a recursive manner.

## Bit manipulation

## Two Pointers
classic example is to remove duplicates from a sorted array
Ex.
1) One slow-runner and the other fast-runner.
2) One pointer starts from the beginning while the other pointer starts from the end.

## Sliding window
- a window is formed over some part of data, and this window can slide over the data to capture different portions of it

## Backtracking
is an algorithmic technique for solving problems recursively by trying to build a solution incrementally, one piece at a time, removing those solutions that fail to satisfy the constraints of the problem at any point in time (by time, here, is referred to the time elapsed till reaching any level of the search tree)

# References
Complete algorithm manual steven skiena
freecodecamp Algo and Data Structures [video](https://www.youtube.com/watch?v=8hly31xKli0)
Grokking Algorithms book

## Categories in blind75
18. Graphs
19. Advanced Graphs
20. 1-D Dynamic Programming
21. 2-D Dynamic Programming
22. Greedy
23. Intervals
24. Math & Geometry
25. Bit Manipulation
