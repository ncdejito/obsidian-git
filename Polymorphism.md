## Concepts
Static polymorphism
Compile time function overloading
Ex. Multiple definitions same function name, differing in parameter types gotten

Dynamic polymorphism
Runtime function overriding
Ex. Select which function to call based on type provided, the virtual function from superclass or the overriding function in the subclass

## Example
Template classes
Templates - apply same class to different data types
Templates
>The simple idea is to pass data type as a parameter so that we don’t need to write the same code for different data types. For example, a software company may need to sort() for different data types.

Function templates
>Examples of function templates are sort(), max(), min(), printArray()

Class templates
>class templates are useful when a class defines something that is independent of the data type. Can be useful for classes like LinkedList, BinaryTree, Stack, Queue, Array, etc.

Operator overloading
>In C++, we can make operators work for user-defined classes. This means C++ has the ability to provide the operators with a special meaning for a data type, this ability is known as operator overloading. For example, we can overload an operator ‘+’ in a class like String so that we can concatenate two strings by just using +.