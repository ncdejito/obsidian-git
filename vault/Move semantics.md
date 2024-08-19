## Concern
Prevent unnecessary copying of large data
Like moving your furniture to a new apartment, vs buying new furniture for the new apartment (From 2022 back to basics vid)

## Actions
Pass by reference using
* void foo(const std::string& arg)
* void foo(std::string& arg)
* void foo(std::string&& arg)

## Components
Lvalue reference & - pass the address of the param
Rvalue reference && - can modify passed param to "steal" the value
Universal reference
* also called forwarding reference
* could be either lvalue or rvalue depending on assigned var
- && with type deduction (either template T&& or auto&&)

Std::move 
Conceptually
Move object instead of copying
Implementation wise
Marks an object may be "moved from"
same as static cast remove_ref &&

Std::forward
Used to achieve perfect forwarding
conditionally casts lvalue to either rvalue or lvalue, depending on type
same as static cast &&

Move constructor 
> work on the r-value references and move semantics(move semantics involves pointing to the already existing object in the memory)
> stdmove

Move assignment operator
operator=(&&)
return * this

## Concepts
[[Binding]]
"Steal" - change binding to new owner
l-value & - name of a variable, memory location that identifies an object, lives until end of scope, a glvalue that is not an xvalue
r-value && - operator evaluations and string literals, data value that is stored at some address in memory which has no name, lives until end of line, a prvalue or an xvalue
glvalue - generalized left, expression whose evaluation determines identity of an object
prvalue - purely right value, computes a value or initializes an object
xvalue - expiring value v2=stdmovev1; xvalue is stdmovev1

E.g. 
s+s=s;
Left is rvalue, right is lvalue

* Handle move or copy properly with [[Rule of Five Three Zero]]

* Perfect forwarding - move semantics for generic code (i.e. templates), uses universal references to make move semantics pass through, reduces the need for unnecessary copying by reducing the need to write overloads to handle rvalue and lvalue separately

* Copy elision - omit copy and move constructors 'of a passed object' resulting in zero-copy pass-by-value semantics

* Return value optimization - type of copy elision, returning in functions applies as much stdmoves as possible

## Reference
Rule of 3/5/0 - from recap section of https://web.stanford.edu/class/cs106l/lectures/14_std_optional_&_type%20safety_S24.pdf
C++ move semantics by josuttis
* Core features for move semantics
* ways to apply move semantics (2.4 overloading by different references)