collection of multiple items under a single variable name
```
# python
arr = [1,2,3]
len(arr)
arr[0] = 1
for item in arr:
	print(item)
```

```
// cpp
#include <iostream>
#include <vector>
int main()
{
    std::vector<int> arr = {1, 2, 3};
    std::cout << arr.size();
    
arr[0] = 1;
arr.push_back(4); // append to end of list

// loop over indices
// for (int i = 0; i < A.size(); ++i)
// loop over items in the list
for (auto i = arr.begin(); i != arr.end(); ++i)
	std::cout << *i << " ";

// check if empty
std::vector<int> arr = {};
if (arr.empty())
	std::cout << "arr is empty";
}
```
[source](https://www.geeksforgeeks.org/vector-in-cpp-stl/)

Vector c++
* Reserve - increase capacity without reallocation
* pushback - add element
* emplaceback - no copying vs pushback