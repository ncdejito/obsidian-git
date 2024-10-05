#job 
[[Understand Behavior Trees]]

Talk to Nav2!
https://huggingface.co/chat/conversation/n_qNYcf

A Survey of Modern & Capable Mobile Robotics Algorithms in ROS2
https://www.linkedin.com/posts/steve-macenski-41a985101_from-the-desks-of-ros-maintainers-a-survey-activity-7091849753952489472-XQcY?utm_source=share&utm_medium=member_desktop

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
	* [[Smoothers]] - reduces path raggedness, smoothing abrupt rotations, increases distance from obstacles and high-cost areas
	* Waypoint following - tells our system how to use navigation to get to multiple destinations
* [[State Estimation]]
* Environmental representation - Layered costmaps
* [Configurable items](https://navigation.ros.org/configuration/index.html)


## Errors
Usual problems  
Different topic name  
Different frame name

## Resources
Nav2 Diagrams by NVIDIA [blog](https://docs.omniverse.nvidia.com/app_isaacsim/app_isaacsim/tutorial_ros2_navigation.html)
Nav2 Training worth 140k per person [blog](https://www.theconstructsim.com/ros2-navigation-training/?utm_source=youtu.be/BmyCi2lcdJY&utm_medium=Description)
Companies using nav2  
[https://www.linkedin.com/posts/steve-macenski-41a985101_ros-nav2-modelpredictivecontrol-activity-7078062878448119808-Qjis](https://www.linkedin.com/posts/steve-macenski-41a985101_ros-nav2-modelpredictivecontrol-activity-7078062878448119808-Qjis)
