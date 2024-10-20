[[Use Nav2]]
## Components
- Nodes - 1 action, only needs to output success or failure, no need to pass info about next action
- Selectors/Fallback - try each child node until first success
- Sequences - arrow, do all child nodes sequentially
- Parallel - runs child nodes in parallel
- Decorators - looping, guarding resource (someone's using the cannon now, no other agent can use it)
## Definition
model for plan execution
describe switchings between a finite set of tasks in a modular fashion
main building block of a behavior is a task rather than a state
Emergent behavior - whole has properties that its individual parts do not have: programming theory, system design

## Pros and Cons
Benefits
Easy to understand
Fast run-time execution
Can be built and tweaked rapidly, especially with graphical tools
Flexible and scalable; complexity of trees can be scaled up and down as needed

Drawbacks
Basically reactive so no real plan or states (good conditions can help)
Naive version only evaluates in left-to-right order (can add priorities)
Naive version also always traverses from root
(solved by event-driven trees) - e.g. if agent gets shot immediately goes to a node of running aware
Slow to respond to urgent events (try monitor-style parallels - e.g. if a player shoots me i should stop doing , did i lose health? do something different)

## Resources
Behavior Trees in AI and Robotics by M. Colledanchise
Visualize ROS2 trees with [Groot](https://navigation.ros.org/tutorials/docs/using_groot.html)
Hierarchical task networks - plan what to do next, same as behavior trees

Alternatives
[[Finite State Machine]]

## Intros
Ed Younskevicius's presentation
[https://www.redblobgames.com/pathfinding/a-star/introduction.html](https://www.redblobgames.com/pathfinding/a-star/introduction.html)  
[https://simblob.blogspot.com/](https://simblob.blogspot.com/)  
[http://www-cs-students.stanford.edu/~amitp/gameprog.html](http://www-cs-students.stanford.edu/~amitp/gameprog.html)  
[https://news.ycombinator.com/item?id=8851408](https://news.ycombinator.com/item?id=8851408)