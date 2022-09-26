[[Backend]], [[Algorithms]], [[Algorithmic Analysis]]

# Data Structures

## Array
- collection of multiple items under a single variable name
```
arr = [1,2,3]
```

## Hashmap
- process of transforming any given key or a string of characters into another value (dictionary = hash map = hash table)
```
dict[key]=value
```

## Stack
- linear data structure that follows the principle of Last In First Out (LIFO). 
```
stack = []
stack.append(1)
stack.append(2)
stack.pop() # outputs 2
```

## Linked list
- linear collection of data elements where each element points to the next. a basic node contains: data, and a reference (in other words, a link) to the next node in the sequence
- The benefit of a linked list over a conventional array is that the list elements can be easily inserted or removed without reallocation or reorganization of the entire structure because the data items need not be stored contiguously in memory or on disk, while **restructuring an array** **at run-time is a much more expensive operation**.

## Trees
- non-linear and a hierarchical data structure consisting of a collection of nodes such that each node of the tree stores a value and a list of references to other nodes (the “children”)

## Tries
- "Retrieval" of data, data structure used to store strings that can be visualized like a graph. It consists of nodes and edges.

## Heap
- a tree where parent and children nodes are ordered hierarchically
- in a max heap, for any given node C, if P is a parent node of C, then the key (the value) of P is greater than or equal to the key of C. In a min heap, the key of P is less than or equal to the key of C.[2] The node at the "top" of the heap (with no parents) is called the root node.

## Priority Queue
- same as queue or stack where each element additionally has a _priority_ associated with it. In a priority queue, an element with high priority is served before an element with low priority
- "queue" is a linear data structure which is FIFO. opposite of stack.

## Others
18. Graphs
19. Advanced Graphs
20. 1-D Dynamic Programming
21. 2-D Dynamic Programming
22. Greedy
23. Intervals
24. Math & Geometry
25. Bit Manipulation