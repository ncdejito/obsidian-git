Creates efficiency by preventing unnecessary copying of large data

Move constructors
l-value & - memory location that identifies an object
r-value && - data value that is stored at some address in memory

Std::move
"Steal"
Move object in the heap instead of copying
same as static cast &&

move constructor
> work on the r-value references and move semantics(move semantics involves pointing to the already existing object in the memory)

Copy semantics
copy constructor
> work with the l-value references and copy semantics(copy semantics means copying the actual data of the object to another object rather than making another object to point the already existing object in the heap