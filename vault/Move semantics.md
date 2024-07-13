Creates efficiency by preventing unnecessary copying of large data

Return value optimization - returning in functions applies as much stdmoves as possible

Copy elision - omit copy and move constructirs resulting in zero-copy passbyvalue semantics

Move constructors
l-value & - memory location that identifies an object, has a name
r-value && - data value that is stored at some address in memory, has no name
xvalue - expiring value v2=stdmovev1; xvalue is stdmovev1

Lvalue reference &
Rvalue reference &&
Universal reference - && with type deduction (either template T&& or auto&&)

E.g. 
s+s=s;
Left is rvalue, right is lvalue
C++ back to basics move semantics

Std::move
"Steal"
Move object in the heap instead of copying
same as static cast &&

move constructor 
> work on the r-value references and move semantics(move semantics involves pointing to the already existing object in the memory)

Move assignment operator
operator=(&&)
Rule of zero c20. If you can avoid defining defaults, do

Copy semantics
copy constructor
> work with the l-value references and copy semantics(copy semantics means copying the actual data of the object to another object rather than making another object to point the already existing object in the heap

Ref
Back to basics move semantics
https://youtu.be/St0MNEU5b0o?si=1lDk3WUzDCSCxFWe
C++ move semantics by josuttis