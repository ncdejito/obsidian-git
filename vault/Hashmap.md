## Hashmap
- process of transforming any given key or a string of characters into another value (dictionary = hash map = hash table)
```
# python
dict = {}
dict[key]=value
```

```
// cpp
#include <iostream>
#include <unordered_map>

int main()
{
    std::unordered_map<std::string, int> dict;

    // inserting values by using [] operator
    dict["GeeksforGeeks"] = 10;
    dict["Practice"] = 20;
    dict["Contribute"] = 30;

    // Traversing an unordered map
    for (auto x : dict)
        std::cout << x.first << " " << x.second << std::endl;

    std::cout << dict["Practice"] << std::endl;
}
```
a Map is ordered by key in increasing order