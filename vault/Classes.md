Combining functions and data in one object
Enables [[Interfaces]]


Class - private by default
```
class Player
{
    string name;
};
```

Struct - public by default
```
struct Player
{
    string name;
    int hp;
    Vector position;
};
int main()
{
    Player me;
    me.name = "William";
    me.hp = 100.0f;
    me.position.x = me.position.y = me.position.z = 0;
}
```
Union - class that can only hold one of its data members at a time, default is public


Access specifiers
Public
Private
Protected - inaccessible outside class but accessible by derived classes, "family secrets"

Friend class - can access private members of another class

