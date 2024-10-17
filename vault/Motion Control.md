Or path integration or tracking
Or [[Remote control]]

Make the robot follow the path by comparing its heading with the error, [[Control theory]] applied on mobile robots

Components
Path - positions
Trajectory - velocities

Methods
* Dynamic window approach DWA - path integration with obstacle avoidance
* Vector Pursuit - better for self driving cars with not much obstacles
https://www.blackcoffeerobotics.com/blog/vector-pursuit-controller-plugin-for-ros2-navigation
* effort controllers - reduce jerkiness of motion https://get-help.theconstruct.ai/t/understanding-the-effort-controller-jointtrajectorycontroller/20787
* Graceful controller - a [[Lyapunov stability]] controller
	* https://github.com/ros-navigation/navigation2/tree/main/nav2_graceful_controller

A convergent dynamic window approach to obstacle avoidance by Ogren  
Done only in simulation

Do not evaluate the velocities in isolation
[https://github.com/locusrobotics/robot_navigation/blob/master/dwb_local_planner%2FREADME.md](https://github.com/locusrobotics/robot_navigation/blob/master/dwb_local_planner%2FREADME.md)

Curves and rrl on objective functions  
[https://www.mdpi.com/1424-8220/18/9/3170](https://www.mdpi.com/1424-8220/18/9/3170)

Techniques focused on stability  
[https://www.researchgate.net/profile/Farah-Kamil/publication/283851753_A_Review_on_Motion_Planning_and_Obstacle_Avoidance_Approaches_in_Dynamic_Environments/links/582ed43608ae138f1c03149c/A-Review-on-Motion-Planning-and-Obstacle-Avoidance-Approaches-in-Dynamic-Environments.pdf?origin=journalDetail&_tp=eyJwYWdlIjoiam91cm5hbERldGFpbCJ9](https://www.researchgate.net/profile/Farah-Kamil/publication/283851753_A_Review_on_Motion_Planning_and_Obstacle_Avoidance_Approaches_in_Dynamic_Environments/links/582ed43608ae138f1c03149c/A-Review-on-Motion-Planning-and-Obstacle-Avoidance-Approaches-in-Dynamic-Environments.pdf?origin=journalDetail&_tp=eyJwYWdlIjoiam91cm5hbERldGFpbCJ9)

Teb timed elastic bands
Weighted multi objective function  
- read on ieee dyson

Mppi - modular and custom cost functions  
Key idea: measure KL divergence between optimal distribution and controller induced distribution


How to add traj costs across path  
https://github.com/ros-navigation/navigation2/blob/main/nav2_mppi_controller/src/critics/path_align_critic.cpp

Modern ml control
https://www.linkedin.com/posts/ardalantajbakhsh_robotics-roboticsresearch-reinforcementlearning-activity-7238311854278651905-Tv25

Nice to know
Reverse is opposite spot turn, cannot both enable
Smac planner no need for optimization based smoothing
Speed limits are masks applied over the whole map
Different method of funneling the control signal
Graceful controller - lyapunov stable, has stability analysis

What are these and can I use them?
softmax mppi - how does mppi enable multi objective function without needing convex and differentiable?
rotate to goal critic - hypotenuse squared (why?)
https://github.com/ros-navigation/navigation2/blob/771eca41bb7b6ad26856c434dd79e48a399c4601/nav2_dwb_controller/dwb_critics/src/rotate_to_goal.cpp#L103C23-L103C31
path inversion in smac
Regulated pure pursuit carrot - used to avoid oscillating when exceeding the goal