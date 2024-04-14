- Object
- Class
- Inheritance - create new classes that are based on existing classes, inheriting their properties and behaviors
- Polymorphism - single interface to deal with different kinds of inputs
	- Templates - apply same class to different data types
- Abstraction
- Encapsulation - bundling data with the functions that use them

Virtual functions

required for base classes and necessary for polymorphism

[[Program in C++]]
Class - private by default
> There is only one difference between class and struct, and it is that the data members inside a struct keyword will be declared public by default, while in a class keyword the data members inside the class will be declared private by default.
```
class Player
{
    string name;
};
```

Struct - public by default
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

Template classes
Templates
>The simple idea is to pass data type as a parameter so that we don’t need to write the same code for different data types. For example, a software company may need to sort() for different data types.

Function templates
>Examples of function templates are sort(), max(), min(), printArray()

Class templates
>class templates are useful when a class defines something that is independent of the data type. Can be useful for classes like LinkedList, BinaryTree, Stack, Queue, Array, etc.

Operator overloading
>In C++, we can make operators work for user-defined classes. This means C++ has the ability to provide the operators with a special meaning for a data type, this ability is known as operator overloading. For example, we can overload an operator ‘+’ in a class like String so that we can concatenate two strings by just using +.

[Notes on OOP](https://www.linkedin.com/posts/kapilyadav22_oops-object-oriented-programming-by-kapil-activity-6965887795018018816-Ftpv?utm_source=share&utm_medium=member_android)

[[Use Interfaces]]