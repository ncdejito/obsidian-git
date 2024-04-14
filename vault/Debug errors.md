Article: when debugging your attitude matters jvns.ca
Bad habits to avoid:
-making random changes to my code in the hopes that it would work
-googling a lot of things and trying them without understanding what they did
-if something broke, reverting my changes and starting again
Learn the basics and see if that helps
Watch people who know what theyre doing

Article: How to debug jvns.ca
Other resources 
-How to Debug David Agans
Reproduce your bug
Reproduce quickly
Accept that its your codes fault
Guess based on your mental model
Start doing experiments
Change one thing at a time
Check your assumptions
Write your code so its easier to debug - limit checks and error handling
Error messages are better than silently failing
Understand what the error messages mean

Breathe
Replicate error
Understand tech fundamentals - read docs
Change one thing at a time

Dealing with clashes against your understanding
Deep breath
What are you trying to do again?
How might you be wrong?
What other things can you try?

Debugging strategies  
When stuck:  
Break down smaller subtasks  
Understand core concepts  
Try solving another problem

Gdb
```
g++ -o hello -g hello.cpp
gdb
file hello // specify what file to check
b main // set breakpoint to "main" function
r // run program
s // step 1 line
p x // print out variable x
n // if next step is function, skip call
c // continue until end
where // list call stack up to where you are in the program
```
https://people.astro.umass.edu/~weinberg/a732/gdb.html#SEC99

lldb
```
breakpoint set -f file.zig -l 156
thread backtrace
```

ChatGDB

Valgrind+gdb detects segfaults