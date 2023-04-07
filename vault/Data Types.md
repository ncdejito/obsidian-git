[[Build Backend Components]]
[[Use appropriate Data Structures]]
[[Use Python]] [[C++]]

Integer
Float
Character

String
```
# python
>>> str = "test"
>>> len(str)
4
>>> str[0:2]
'te'
>>> str + "test"
'testtest'
```

```
// cpp
#include <iostream>
#include <string>

int main()
{
    std::string str = "test";
	std::cout << str.size() << std::endl;
    std::cout << str.substr(0, 2) << std::endl;
    
    std::string str1 = "test";
    std::string str2 = "test2";
    std::string str = str1 + str2;
    std::cout << str << std::endl;
}
```


String interning
makes some string processing tasks more time- or space-efficient at the cost of requiring more time when the string is created or interned

method of storing only one copy of each distinct string value, which must be immutable