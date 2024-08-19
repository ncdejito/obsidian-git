Concern
Ensure memory is allocated and deallocated properly

Definition
- Rule of Zero: if you have self-managing member variables, and don’t need to define custom constructors, and operators, then don’t! c20. If you can avoid defining defaults, do

- Rule of Three: if you define a custom destructor then you need to also define a custom copy constructor and copy assignment operator.

- Rule of Five: If you have a custom copy constructor, and copy assignment operator, then you should also define a move constructor and a move assignment operator

Reference
https://en.cppreference.com/w/cpp/language/rule_of_three
