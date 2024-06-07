[[C++]] [[Program in Rust]]

[[Pointers]]
[[Move semantics]]
[[Copy semantics]]

## Concepts
Stack vs Heap Memory Allocation
Stack - limited memory, freed up on exit
> allocation happens on contiguous blocks of memory. We call it a stack memory allocation because the allocation happens in the function call stack. The size of memory to be allocated is known to the compiler and whenever a function is called, its variables get memory allocated on the stack.

Heap - (dynamic memory), free pool of memory, remains on exit must be freed explicity
> memory is allocated during the execution of instructions written by programmers. Note that the name heap has nothing to do with the heap data structure. It is called heap because it is a pile of memory space available to programmers to allocate and de-allocate.

Stack - expands and contracts at runtime, function calls
Heap - not the data structure, an area of a process’s virtual memory that can be allocated dynamically

[Pointers and dynamic memory - stack vs heap](https://www.youtube.com/watch?v=_8-ht2AKyH4&list=PL2_aWCzGMAwLZp6LMUKI3cc7pgGsasm2_&index=12&t=937s)

## Dynamic memory allocation

when to use & - if with & pass by reference, can edit the value inside the function. if no & pass by value, cannot edit value inside function
```
void function(type& variable_name) vs void function(type variable_name)
```

performing memory allocation manually by programmer
```
// C++ style
int main()
{ // "dynamic allocation" – using keyword new!
    Player *player = new Player();
    delete player; // deletion invokes dtor
}
```

malloc - allocates a block of uninitialized memory to a pointer
```
// C style
  // allocate memory of int size to an int pointer
  int* ptr = (int*) malloc(sizeof(int));

  // assign the value 5 to allocated memory
  *ptr = 5;

free(ptr);
```

Buffer - denotes a computer memory block that acts as a temporary placeholder
```
Char* buff = new char [ ]
```
[source](https://www.educba.com/c-plus-plus-buffer/)

C - malloc, calloc, realloc and free. C++ -  new and delete 

Methods
Malloc - returns a pointer to a block of memory of at least size bytes that is suitably aligned for any kind of data object that might be contained in the block
Free - delete contents of block so that it can be used for other things

## References
* Memory management in Computer Systems Programmer's Perspective