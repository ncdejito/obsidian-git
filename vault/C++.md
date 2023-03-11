[[Programming Languages]]

Compile program and run (Linux)
```
g++ -o hello hello.cpp
chmod a+x hello
./hello

g++ -o hello *.cpp // compile all cpp files in directory

// treat warnings as error, used c++20 as standard
g++ -Wall -Weffc++ -Wextra -Wsign-conversion -Werror -std=c++2a main.cpp io.cpp -o main
```
Import functions using header files
```
// passorfail.h
#ifndef PASSORFAIL_H
#define PASSORFAIL_H

bool passOrFail();

#endif
```



## References
How to learn (start anywhere!)
* C++ for everyone by Dr. Ira Pohl
* learncpp.com
* Effective Modern C++ (book)
* [Rockstar](https://github.com/avinassh/rockstar) Learn c++ with python
* FunctionalPlus [code](https://github.com/Dobiasd/FunctionalPlus)
* observable [code](https://github.com/ddinu/observable)
* Functional c++ [blogpost](https://learn.microsoft.com/en-us/archive/msdn-magazine/2012/august/c-functional-style-programming-in-c)
* How to program functionally in c++ [blogpost](https://medium.com/swlh/doing-it-the-functional-way-in-c-5c392bbdd46a)
* CTest CMake
* GDB
* Robotics with Sina recos
* Top 10 courses for beginners [medium](https://medium.com/javarevisited/top-10-courses-to-learn-c-for-beginners-best-and-free-4afc262a544e)

Modern C++  
[https://github.com/facebook/folly](https://github.com/facebook/folly)



## Constructs
[[Data Structures]]

Class
> There is only one difference between class and struct, and it is that the data members inside a struct keyword will be declared public by default, while in a class keyword the data members inside the class will be declared private by default.
```
class Player
{
    string name;
};
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
	int num;
    int* ptr = (int*) malloc(sizeof(int));
    ptr = &num;
    *ptr = newval; // change variable content
    
    Player *ptrMe;
    ptrMe = &me;
    ptrMe->name = "John"; // changed name to John
```

[source](https://www3.ntu.edu.sg/home/ehchua/programming/cpp/cp4_PointerReference.html)
```
/* Test pointer declaration and initialization (TestPointerInit.cpp) */
#include <iostream>
using namespace std;
 
int main() {
   int number = 88;    // Declare an int variable and assign an initial value
   int * pNumber;      // Declare a pointer variable pointing to an int (or int pointer)
   pNumber = &number;  // assign the address of the variable number to pointer pNumber
 
   cout << pNumber << endl;  // Print content of pNumber (0x22ccf0)
   cout << &number << endl;  // Print address of number (0x22ccf0)
   cout << *pNumber << endl; // Print value pointed to by pNumber (88)
   cout << number << endl;   // Print value of number (88)
 
   *pNumber = 99;            // Re-assign value pointed to by pNumber
   cout << pNumber << endl;  // Print content of pNumber (0x22ccf0)
   cout << &number << endl;  // Print address of number (0x22ccf0)
   cout << *pNumber << endl; // Print value pointed to by pNumber (99)
   cout << number << endl;   // Print value of number (99)
                             // The value of number changes via pointer
 
   cout << &pNumber << endl; // Print the address of pointer variable pNumber (0x22ccec)
}
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


CMakeLists.txt
> defines instructions, source files and target executables in compiling c++ code

h file vs c file - header file, like a set of params shared across files