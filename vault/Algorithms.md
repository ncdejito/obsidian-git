[[Backend]], [[Algorithmic Analysis]], [[Data Structures]]

# Algorithms

## Sorting
Time complexity - O(nlogn)

Merge Sort - an example of the divide and conquer strategy, array is initially divided into two equal halves and then they are combined in a sorted manner

Insertion Sort - a sorting algorithm that places an unsorted element at its suitable place in each iteration

Heap Sort - a comparison-based sorting technique based on Binary Heap data structure. It is similar to the selection sort where we first find the minimum element and place the minimum element at the beginning. Repeat the same process for the remaining elements.

## Two Pointers
classic example is to remove duplicates from a sorted array
Ex.
1) One slow-runner and the other fast-runner.
2) One pointer starts from the beginning while the other pointer starts from the end.

## Sliding window
- a window is formed over some part of data, and this window can slide over the data to capture different portions of it

## Binary search
an efficient algorithm for finding an item from a sorted list of items. It works by repeatedly dividing in half the portion of the list that could contain the item, until you've narrowed down the possible locations to just one
Ex. Find a word in a dictionary

## Backtracking
is an algorithmic technique for solving problems recursively by trying to build a solution incrementally, one piece at a time, removing those solutions that fail to satisfy the constraints of the problem at any point in time (by time, here, is referred to the time elapsed till reaching any level of the search tree)

## Dynamic programming 
= recursion + memoization
>simplifying a complicated problem by breaking it down into simpler sub-problems in a recursive manner.