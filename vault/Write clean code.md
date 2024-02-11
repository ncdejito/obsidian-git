

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

Code review
[AI-powered review](https://reviewify.io/)

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

Ruler