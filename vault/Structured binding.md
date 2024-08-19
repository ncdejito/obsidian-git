Structured [[Binding]] (since c++17)
> Binds the specified names to subobjects or elements of the initializer.
> Like [[References]], a structured binding is an alias to an existing object. Unlike a reference, a structured binding does not have to be of a reference type.

```
int a[2] = {1, 2};
 
auto [x, y] = a;    // creates e[2], copies a into e,
                    // then x refers to e[0], y refers to e[1]
auto& [xr, yr] = a; // xr refers to a[0], yr refers to a[1]
```