
[[Pointer bugs]]

Smart pointers - ensure objects are deleted once pointers go out of scope

Unique - only 1 owner
```
std::unique_ptr up = make_unique<objecttype>();
up.reset();
*up // get object itself
std::move(up) // up is automatically set to null
```

Shared - multiple owners
Weak

`*&` operators https://en.cppreference.com/w/cpp/language/operator_member_access

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
