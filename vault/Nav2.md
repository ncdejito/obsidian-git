
## Components
* [[Nav2 Nodes]]
* [[Nav2 Topics]]
* [[Nav2 Services]]
* [[Nav2 Actions]]


## Concepts
* [[ROS2]]
	* Lifecycle Nodes
* Behavior Trees
* Navigation servers
	* Planners - computes paths to complete some objective function, like shortest paths, complete coverage paths
	* Controllers - follows paths
	* Behaviors - recovery, can ask for help from operator via SMS/email
	* Smoothers - reduces path raggedness, smoothing abrupt rotations, increases distance from obstacles and high-cost areas
	* Waypoint following - tells our system how to use navigation to get to multiple destinations
* State Estimation
* Environmental representation
* [Configurable items](https://navigation.ros.org/configuration/index.html)


## Errors
usual problems  
Different topic name  
Different frame name