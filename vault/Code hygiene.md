[[Software Eng Best Practices]]

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


Code best practices
- DRY - don’t repeat yourself
- KISS - keep it simple stupid, keep it short and simple
- YAGNI - you aren’t gonna need it, “Always implement things when you actually need them, never when you just foresee that you need them”

Code review
[AI-powered review](https://reviewify.io/)
