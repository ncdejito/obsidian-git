Change functionality when an object is declared

Function specifiers
* inline - when function is called by a specific line, it is expanded in that line
* virtual - declared within a base class, allows function call in derived when base is referenced
* override - in derived class, overrides a virtual function from the base class
* final - virtual function cannot be overridden by derived class
* static - function can be called from class without an object
* function const - cannot modify objects inside class
* noexcept - specifies whether a function can throw exceptions

Object specifiers
* static - object exists in the whole lifetime of the program
* const param - object cannot be modified
* typedef - defines a custom type
* constexpr

Pointer qualifier
* type * const - cannot point to anything else
* const type* - pointer to a const object, can be changed where it points, but cannot change object using pointer

Reference
Declaration specifiers
https://en.cppreference.com/w/cpp/language/declarations