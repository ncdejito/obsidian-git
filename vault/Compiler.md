Compile program and run (Linux)
```
g++ -o hello hello.cpp
chmod a+x hello
./hello

g++ -o hello *.cpp // compile all cpp files in directory

// treat warnings as error, used c++20 as standard
g++ -Wall -Weffc++ -Wextra -Wsign-conversion -Werror -std=c++2a main.cpp io.cpp -o main

c++14
-std=c++14
```

Clang compiles faster than gcc

Run compiler first before building the binary - clang your_file.cpp -fsyntax-only - doesnt work with containers environment

CMakeLists.txt
> defines instructions, source files and target executables in compiling c++ code

If long errors, probably a template error

SConscript

onlinegdb

Distribute compile across machines
github:icecc/icecream