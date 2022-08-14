Why
>C++ is faster than Python because **it is statically typed**, which leads to a faster compilation of code. Python is slower than C++, it supports dynamic typing, and it also uses the interpreter, which makes the process of compilation slower.


Compile program and run (Linux)
```
g++ -o hello hello.cpp
chmod a+x hello
./hello
```

## Objects
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
Pointers
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


## Dynamic memory allocation
performing memory allocation manually by programmer
```
int main()
{ // "dynamic allocation" – using keyword new!
    Player *player = new Player();
    delete player; // deletion invokes dtor
}
```

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