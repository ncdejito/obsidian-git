[[Understand Behavior Trees]]

## Components
* [[Nav2 Nodes]]
* [[Nav2 Topics]]
* [[Nav2 Messages]]
* [[Nav2 Services]]
* [[Nav2 Actions]]


## Concepts
* [[Use ROS2]]
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

## Resources
Nav2 Diagrams by NVIDIA [blog](https://docs.omniverse.nvidia.com/app_isaacsim/app_isaacsim/tutorial_ros2_navigation.html)
Nav2 Training worth 140k per person [blog](https://www.theconstructsim.com/ros2-navigation-training/?utm_source=youtu.be/BmyCi2lcdJY&utm_medium=Description)