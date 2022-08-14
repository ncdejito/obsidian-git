Why
>C++ is faster than Python because **it is statically typed**, which leads to a faster compilation of code. Python is slower than C++, it supports dynamic typing, and it also uses the interpreter, which makes the process of compilation slower.


Compile program and run (Linux)
```
g++ -o hello hello.cpp
chmod a+x hello
./hello
```

## Objects
Unordered map - hashmap, dict
```
    unordered_map<string, int> umap;
  
    // inserting values by using [] operator
    umap["GeeksforGeeks"] = 10;
    umap["Practice"] = 20;
    umap["Contribute"] = 30;
```

Struct
```
struct Player
{
    string name;
    int hp;
    Vector position;
};
int main()
{
    Player me;
    me.name = "William";
    me.hp = 100.0f;
    me.position.x = me.position.y = me.position.z = 0;
}
```

Pointers - manipulate the variable that is pointed to through the pointer. Otherwise you'll get heap-buffer-overflow error
```
    Player *ptrMe;
    ptrMe = &me;
    ptrMe->name = "John"; // changed name to John
```

Class
> There is only one difference between class and struct, and it is that the data members inside a struct keyword will be declared public by default, while in a class keyword the data members inside the class will be declared private by default.
```
class Player
{
    string name;
};
```

Structured bindings (since c++17)
> Like a reference, a structured binding is an alias to an existing object. Unlike a reference, a structured binding does not have to be of a reference type.


## Concepts

Dynamic memory allocation - performing memory allocation manually by programmer
```
int main()
{ // "dynamic allocation" – using keyword new!
    Player *player = new Player();
    delete player; // deletion invokes dtor
}
```

Stack vs Heap Memory Allocation
Stack
> allocation happens on contiguous blocks of memory. We call it a stack memory allocation because the allocation happens in the function call stack. The size of memory to be allocated is known to the compiler and whenever a function is called, its variables get memory allocated on the stack.

Heap
> memory is allocated during the execution of instructions written by programmers. Note that the name heap has nothing to do with the heap data structure. It is called heap because it is a pile of memory space available to programmers to allocated and de-allocate.

malloc - allocates a block of uninitialized memory to a pointer
```
  // allocate memory of int size to an int pointer
  int* ptr = (int*) malloc(sizeof(int));

  // assign the value 5 to allocated memory
  *ptr = 5;
```

Buffer - denotes a computer memory block that acts as a temporary placeholder
```
Char* buff = new char [ ]
```
[source](https://www.educba.com/c-plus-plus-buffer/)

## Advanced
STL
>set of C++ template classes to provide common programming data structures and functions such as lists, stacks, arrays, etc. It is a library of container classes, algorithms, and iterators

Template classes
Templates
>The simple idea is to pass data type as a parameter so that we don’t need to write the same code for different data types. For example, a software company may need to sort() for different data types.

Function templates
>Examples of function templates are sort(), max(), min(), printArray()

Class templates
>class templates are useful when a class defines something that is independent of the data type. Can be useful for classes like LinkedList, BinaryTree, Stack, Queue, Array, etc.

Operator overloading
>In C++, we can make operators work for user-defined classes. This means C++ has the ability to provide the operators with a special meaning for a data type, this ability is known as operator overloading. For example, we can overload an operator ‘+’ in a class like String so that we can concatenate two strings by just using +.

Lambda expressions
> way of defining an anonymous function object (a _closure_) right at the location where it's invoked or passed as an argument to a function

Move constructors
l-value - memory location that identifies an object
r-value - data value that is stored at some address in memory
copy constructor
> work with the l-value references and copy semantics(copy semantics means copying the actual data of the object to another object rather than making another object to point the already existing object in the heap)

move constructor
> work on the r-value references and move semantics(move semantics involves pointing to the already existing object in the memory)