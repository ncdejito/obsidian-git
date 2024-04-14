#job 

[[Program in Object-Oriented]]
[[Virtual Memory Management]]
[[Concurrency]]

[C++ Developer](https://www.udacity.com/course/c-plus-plus-nanodegree--nd213) - 4months memory management and concurrency

onlinegdb - quick prototyping

Compile program and run (Linux)
```
g++ -o hello hello.cpp
chmod a+x hello
./hello

g++ -o hello *.cpp // compile all cpp files in directory

// treat warnings as error, used c++20 as standard
g++ -Wall -Weffc++ -Wextra -Wsign-conversion -Werror -std=c++2a main.cpp io.cpp -o main

c++14
-std=c++14
```
Import functions using header files
```
// passorfail.h
#ifndef PASSORFAIL_H
#define PASSORFAIL_H

bool passOrFail();

#endif
```

Clang compiles faster than gcc

Run compiler first before building the binary - clang your_file.cpp -fsyntax-only - doesnt work with containers environment

https://github.com/TheAlgorithms/C-Plus-Plus

## References
How to learn (start anywhere!)
* C++ for the impatient
* Effective modern c++
* C++ for everyone coursera by Dr. Ira Pohl
* Learncpp .com
[Awesome c++ blogs](https://www.linkedin.com/posts/necatiergn_cpp-programming-coding-activity-7053297104751865857-OyVR?utm_source=share&utm_medium=member_desktop)

Modern C++  
[https://github.com/facebook/folly](https://github.com/facebook/folly)
* [Rockstar](https://github.com/avinassh/rockstar) Learn c++ with python
* FunctionalPlus [code](https://github.com/Dobiasd/FunctionalPlus)
* observable [code](https://github.com/ddinu/observable)
* Functional c++ [blogpost](https://learn.microsoft.com/en-us/archive/msdn-magazine/2012/august/c-functional-style-programming-in-c)
* How to program functionally in c++ [blogpost](https://medium.com/swlh/doing-it-the-functional-way-in-c-5c392bbdd46a)
* CTest CMake
* GDB
* Robotics with Sina recos
* Top 10 courses for beginners [medium](https://medium.com/javarevisited/top-10-courses-to-learn-c-for-beginners-best-and-free-4afc262a544e)
## Constructs
[[Data Structures]]

Structured bindings (since c++17)
> Like a reference, a structured binding is an alias to an existing object. Unlike a reference, a structured binding does not have to be of a reference type.


STL
>set of C++ template classes to provide common programming data structures and functions such as lists, stacks, arrays, etc. It is a library of container classes, algorithms, and iterators

CMakeLists.txt
> defines instructions, source files and target executables in compiling c++ code

h file vs c file - header file, like a set of params shared across files


