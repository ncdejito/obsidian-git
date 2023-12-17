

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

lldb
```
breakpoint set -f file.zig -l 156
thread backtrace
```

ChatGDB

Valgrind+gdb detects segfaults