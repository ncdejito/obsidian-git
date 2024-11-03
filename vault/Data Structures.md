[[Build Backend Components]], [[Algorithms]]

[Data Structures and Algorithms](https://www.udacity.com/course/data-structures-and-algorithms-nanodegree--nd256) - 4months 100 exercises and mentor support

[[Array]]
- 
[[Hashmap]]

## Linked list
- linear collection of data elements where each element points to the next. a basic node contains: data, and a reference (in other words, a link) to the next node in the sequence
- The benefit of a linked list over a conventional array is that the list elements can be easily inserted or removed without reallocation or reorganization of the entire structure because the data items need not be stored contiguously in memory or on disk, while **restructuring an array** **at run-time is a much more expensive operation**.

## Queues
```
queue<int> q;
if !q.empty()
q.push(x);
q.front();
q.pop();
```
## Trees
- non-linear and a hierarchical data structure consisting of a collection of nodes such that each node of the tree stores a value and a list of references to other nodes (the “children”)

## Graphs

## Advanced

### Multi-dimension arrays, matrices, tensors
Python
numpy
pytorch

cpp
std::vector - workable but tedious

### Union-find data structure

### Priority Queue
- same as queue or stack where each element additionally has a _priority_ associated with it. In a priority queue, an element with high priority is served before an element with low priority
- "queue" is a linear data structure which is FIFO. opposite of stack.

### Stack
- linear data structure that follows the principle of Last In First Out (LIFO). 
```
stack = []
stack.append(1)
stack.append(2)
stack.pop() # outputs 2
```


### Tries
- "Retrieval" of data, also called digital tree or prefix tree, is a type of k-ary search tree, a tree data structure used for locating specific keys from within a set

### Heap
- a tree where parent and children nodes are ordered hierarchically
- in a max heap, for any given node C, if P is a parent node of C, then the key (the value) of P is greater than or equal to the key of C. In a min heap, the key of P is less than or equal to the key of C.[2] The node at the "top" of the heap (with no parents) is called the root node.





## References
[freecodecamp](https://www.youtube.com/watch?v=RBSGKlAvoiM)
[Illustrated](https://www.youtube.com/watch?v=9rhT3P1MDHk&list=PLkZYeFmDuaN2-KUIv-mvbjfKszIGJ4FaY)
https://github.com/donnemartin/interactive-coding-challenges

CTCI
Geeks4Geeks Algorithms
Steven skiena algos
grokking algorithms
Freecodecamp Algos
Illustrated
Freecodecamp DS
Data structures quiwa
