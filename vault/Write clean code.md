
Principle: Quickfixes first then if gone back to, refactor to cleaner ones
- Nonredundant - no copy paste of blocks of text
- Modular - complex steps done in 1 function/cell
- Well documented - docstrings
- Concise documentation in notebook
	- -On-demand verbosity - can set if you want to see everything or not, logging?
	- -long functions in another py script
	- -no unecessarily long comments
- Consistent conventions
	- -No reassignments
	- -No prefixing df_ like in df_train
	- -Never use df, df_, df_tmp, df0 just use df1, df2, df3, rename if necessary
	- -Use _ or df only when you dont care about the output/it's intermediate only
	- -df names related to nb section header? Eg. Consolidate header: cons1 cons2

https://codeburst.io/a-short-summary-on-clean-coding-best-practices-d8afbfa7677?gi=231d837ffe6
https://codewithoutrules.com/2018/11/02/when-clean-up-your-code/

Immutable
functional

Static typing
- improves performance with less checks on runtime
Why
- static typing for performance - less steps for checking on runtime (is this a sum of 2 ints? sum of 2 str?)
- typing catches a lot of errors
- usually observed in compiled languages

Closures
also lexical closure or function closure, is a technique for implementing lexically scoped name binding in a language with first-class functions.

Mary:
ish - scope is first introduced in https://craftinginterpreters.com/statements-and-state.html#scope and then a first pass at closures in https://craftinginterpreters.com/functions.html#local-functions-and-closures and then this chapter is more about getting it fully correct https://craftinginterpreters.com/resolving-and-binding.html 

Article: write code that is easy to delete
Copy paste code, dont copy paste code
-building reusable code is often done in hindsight so dont preempt too much with features you expect to use in the future
-Make a function only when youve Copy pasted code a couple of times
Make boilerplates, dont make boilerplates
-Make templates of how to use your functions
-If it's too long, wrap it in a simpler to use api e.g. requests vs urllib3
-build simple to use libraries on top of simpler to implement ones
Write a big lump of code
-Its ok to make quick and dirty hacks, cut corners to save time resulting in long trashy code that somehow holds it together
-You should be trying to make new mistakes each time, take new risks, and slowly build up through iteration
-It’s easier to delete all of the code than to delete it piecewise - dont be sad when you delete your old code
Perlis-""Everything should be built top-down, except the first time
""Becoming a professional software developer is accumulating a back-catalogue of regrets and mistakes. You learn nothing from success. It is not that you know what good code looks like, but the scars of bad code are fresh in your mind.
Break your code into pieces
""We isolate the most frustrating parts to write, maintain, or delete away from each other. … We are not building modules around being able to re-use them, but being able to change them
Loose coupling - being able to change your mind without changing too much code.
Keep writing code
Your code should be able to handle change, aka you can write experiments while modifying old code as little as possible
Feature flag - or toggle, used to hide enable or disable feature at runtime


References
Clean Code by Robert C Martin