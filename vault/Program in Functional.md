
Why functional - 
* allows programs to be written in a declarative and composable style, where small functions are combined in a modular manner.
* restricting side effects, programs can have fewer bugs, be easier to debug and test
* good for distributed systems
* Personal experience - easier unit tests, better interfaces

[Thinking Functionally in C++ - Brian Ruth - CppCon 2023 (youtube.com)](https://www.youtube.com/watch?v=6-WH9Hnec1M)
Code categories
 - Actions - depends on how many times they are called
 - Calculations - depends only on their inputs
 - Data - stores input and output data

Lambda expressions
> way of defining an anonymous function object (a _closure_) right at the location where it's invoked or passed as an argument to a function

[Monad](http://www.jerf.org/iri/post/2958)
Monad transformer
Dependent types - a type whose definition depends on a value

### Example
```
// C++20
vector<int> positives = {};
auto get_positive = [](int num)
{ return num > 0; };
copy_if(A.begin(), A.end(), back_inserter(positives), get_positive);
A = positives;
```
* C++ functionalPlus [code](https://github.com/Dobiasd/FunctionalPlus)
* Functional c++ [blogpost](https://learn.microsoft.com/en-us/archive/msdn-magazine/2012/august/c-functional-style-programming-in-c)
* How to program functionally in c++ [blogpost](https://medium.com/swlh/doing-it-the-functional-way-in-c-5c392bbdd46a)

Functional Go
https://github.com/IBM/fp-go

Implementations
[[Haskell]]
[Lean](https://leanprover.github.io/about/)
[[Clojure]]