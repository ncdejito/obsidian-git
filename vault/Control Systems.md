Motion control
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

https://github.com/pnnl/neuromancer

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

Control theory
Concern
objective is to develop a model or algorithm governing the application of system inputs to drive the system to a desired state, while minimizing any delay, overshoot, or steady-state error and ensuring a level of control stability; often with the aim to achieve a degree of optimality.

Control algorithms
pid controller
mpc controller - more used in industry
ESC - electronic speed controllers

Fundamental problems
Lqr
Lqg

Paradigms
Classical control - stick with this first
[[Adaptive control]]
[[Optimal control]]

Concepts
gravity and dynamics compensation control laws, force control, impedance control
Control architecture design
Nonlinear control techniques
Feedback linearization
Sliding mode control
Backstepping

[[Lyapunov stability]]

Classic Controls, Feedback/Feedforward controllers, Cascade control systems
fast control prototyping systems such as speedgoat, xPC, or any other type of real-time machine

Mdp - Markov decision process [[Markov process]]
Maximize future reward with decision making under uncertainty

Feedback control systems simplified
https://www.linkedin.com/posts/muhammad-luqman-%F0%9F%87%B5%F0%9F%87%B8-9b227a11b_controls-controlsystems-controltheory-activity-7180968275277737984-qBtI?utm_source=share&utm_medium=member_android

Steve Brunton also has an awesome youtube channel on dynamic systems, control, and machine learning.

Brian Douglas youtube channel on control systems


Gradient descent
Lipschitz continuity
Probabilistic robotics book
X Ros2 controller papers
Hyunggi optimization resources
X Robotics graduate books

References
All you need to know about control theory
https://youtu.be/lBC1nEq0_nk?si=Bkm_v5Pg89YezVYF

By MIT
https://underactuated.csail.mit.edu/

**

Introductions

### Yoshikawa, T., 1990. Foundations of robotics: analysis and control

- pretty short, good overview

1. Overview of robotic mechanisms and controller - A robot system generally consists of three subsystems: a motion subsystem,a recognition subsystem, and a control subsystem. Book is less focused on recognition; first part on motion, second on control.
    

1. Mechanisms - types of arm mechanisms, wrist mechanisms, degeneracy problem (?), combining arm and wrist creates six degrees of freedom
    
2. Controller - fundamental goals of manipulators, types of control: position control and force control, examples of sensors located in joints
    

3. Kinematics - studying geometrically the motion of the manipulator links and/or
    

objects related to the manipulation task in terms of position, velocity, and acceleration

3. Dynamics - study of forces and their effects on motion. difference between Lagrangian and Newton-Euler formulation, derivation of dynamics equation using formulations, use of equations, required amount of computation, identification method for inertial parameters of manipulators
    
4. Manipulability - evaluating quantitatively ability of manipulators to easily arbitrarily change position and orientation of end effector at tip of manipulator, from the viewpoints of kinematics and dynamics. Not included: size of workspace, positioning accuracy, load capacity, speed, reliability, safety, cost, ease of operation, and settling time
    
5. Position Control - control algos and construction of control systems, methods for determining desired trajectory through given points
    
6. Force Control - ways to control force exerted by robot to objects, types of force control: impedance control (adjust stiffness against force of end effector vs external orces), hybrid control (two feedback loops for separate control of position and force)
    
7. Control of Redundant Manipulators - manipulator has redundancy if it has more degrees of freedom than are necessary to perform a given task, advantages disadvantages of redundant manipulators, method for actively utilizing redundancy to avoid obstacles and singular configurations (?)
    

  

### Spong, Mark W., and Mathukumalli Vidyasagar 2004. Robot dynamics and control

*

1. Introduction - history, components and structure of robots, outline of the text. Included: kinematics, dynamics, motion planning, computer vision, and control, Not included: locomotion, grasping, AI, computer architectures, programming languages, computer-aided design
    
2. Rigid Motions and Homogeneous Transformations - rigid - unable to bend or be forced out of shape, homogeneous transformation - combines rotation and translation into a single matrix multiplication, represent points and vectors in Euclidean space with coordinate frames, rotation matrix
    
3. Forward Kinematics: The Denavit-Hartenberg Convention - relationship between the individual joints of the robot manipulator and the position and orientation of the tool or end-effector
    
4. Inverse Kinematics - determining values for the joint variables that achieve a desired position and orientation for the end-effector
    
5. Velocity Kinematics -- The Manipulator Jacobian - velocity relationships of (1) linear and angular velocities of end-effector, and (2) joint velocities; uses of Jacobian matrix in robotic manipulation (ex: planning and execution of smooth trajectories, execution of coordinated anthropomorphic motion)
    

1. Singular Configurations - manipulator loses one or more degrees of freedom
    

7. Computer Vision
    

1. Geometry of Image Formation - geometric relationship between objects in the world and their projections in an image
    
2. Camera Calibration - calibrating camera to match image pixel coordinate to coordinate in the real world
    
3. Segmentation by Thresholding - separate objects from backgrounds by setting threshold on gray-ness of pixel values
    
4. Component labelling - differentiating objects based on adjacent pixels (if it’s disconnected/not adjacent, means it’s a different object)
    
5. Position and Orientation - compute position and orientation in industrial applications, i.e. depth (distance to object) is fixed
    

9. Path Planning and Collision Avoidance - configuration space, artificial potential fields, random motions to escape local minima, probabilistic roadmap method
    
10. Trajectory Planning - what should be the joint velocities and accelerations while traversing the path, chapter seems incomplete and looks like a draft??
    
11. Dynamics - describe the relationship between force and motion (vs kinematics describe motion without considering forces that produce the motion), Euler-Lagrange equations, holonomic constraints, Principle of Virtual Work, Lagrangian of the system, Newton-Euler formulation
    
12. Independent Joint Control - techniques to derive a control law for each joint of a manipulator based on a single-input/single-output model
    
13. Multivariable Control - control problem in context of whole system of joints
    
14. Force Control - strategies for controlling force of end-effector to objects
    
15. Feedback Linearization - construct a nonlinear control law that exactly linearizes the nonlinear system after a suitable state space change of coordinates
    

  
  

Craig 2005 Intro to robotics

  

### Lynch, K.M. and Park, F.C., 2017. Modern Robotics. 

- touches on many topics and is approachable

1. Preview
    
2. Configuration Space - a specification of the positions of all points of the robot
    
3. Rigid-Body Motions
    
4. Forward Kinematics
    
5. Velocity Kinematics and Statics - statics - analysis of loads acting on physical systems that do not experience an acceleration
    
6. Inverse Kinematics
    
7. Kinematics of Closed Chains - Any kinematic chain that contains one or more loops,  focused on parallel mechanisms (consisting of fixed and moving platforms connected by a set of “legs”)
    
8. Dynamics of Open Chains - study of motion taking into account forces and torques that cause them
    
9. Trajectory Generation - robot position as a function of time, time scaling (specifies the time when those configurations are reached)
    
10. Motion Planning - problem of finding a robot motion from a start state to a goal state that avoids obstacles in the environment and satisfies other constraints, such as joint limits or torque limits
    
11. Robot Control - motion control, force control, hybrid motion-force control, or impedance control
    
12. Grasping and Manipulation - contact kinematics; contact force modelling; and the dynamics of rigid bodies
    
13. Wheeled Mobile Robots - kinematic model of a mobile robot governs how wheel speeds map to robot velocities  
      
    

Specialized  
  
Tsai, L.W., 1999. Robot analysis: the mechanics of serial and parallel manipulators. - very thorough on kinematics


### Ogata 2010. Modern Control Engineering 

*- concerned with modelling, analysis and design of control systems important for robotic systems

1. Introduction to Control Systems
    
2. Mathematical Modeling of Control Systems
    
3. Mathematical Modeling of Mechanical Systems and Electrical Systems
    
4. Mathematical Modeling of Fluid Systems and Thermal Systems
    
5. Transient and Steady-State Response Analyses
    
6. Control Systems Analysis and Design by the Root-Locus Method
    
7. Control Systems Analysis and Design by the Frequency-Response Method
    
8. PID Controllers and Modified PID Controllers
    
9. Control Systems Analysis in State Space
    
10. Control Systems Design in State Space
    



Siciliano, B., Sciavicco, L., Villani, L. and Oriolo, G., 2010. Robotics: modelling, planning and control

Control systems
[[Robotics Software Engineering]]
[[Electronics Engineering]]
[[State estimation]]

Concern
objective is to develop a model or algorithm governing the application of system inputs to drive the system to a desired state, while minimizing any delay, overshoot, or steady-state error and ensuring a level of control stability; often with the aim to achieve a degree of optimality.

make the robot follow the path by comparing its heading with the error
pid controller
mpc controller - more used in industry
ESE - from Kurt

[[Adaptive control]]
[[Optimal control]]

Classic Controls, Feedback/Feedforward controllers, Cascade control systems
fast control prototyping systems such as speedgoat, xPC, or any other type of real-time machine

linear and non-linear feedback control system design

Feedback control systems simplified
https://www.linkedin.com/posts/muhammad-luqman-%F0%9F%87%B5%F0%9F%87%B8-9b227a11b_controls-controlsystems-controltheory-activity-7180968275277737984-qBtI?utm_source=share&utm_medium=member_android

Steve Brunton also has an awesome youtube channel on dynamic systems, control, and machine learning.

Brian Douglas youtube channel on control systems

[[Guidance Navigation and Controls (GNC)]]

LQR implementation
https://github.com/MarwanZaghloul/lqr_local_planner_plugin

**

Introductions

### Yoshikawa, T., 1990. Foundations of robotics: analysis and control

- pretty short, good overview

1. Overview of robotic mechanisms and controller - A robot system generally consists of three subsystems: a motion subsystem,a recognition subsystem, and a control subsystem. Book is less focused on recognition; first part on motion, second on control.
    

1. Mechanisms - types of arm mechanisms, wrist mechanisms, degeneracy problem (?), combining arm and wrist creates six degrees of freedom
    
2. Controller - fundamental goals of manipulators, types of control: position control and force control, examples of sensors located in joints
    

3. Kinematics - studying geometrically the motion of the manipulator links and/or
    

objects related to the manipulation task in terms of position, velocity, and acceleration

3. Dynamics - study of forces and their effects on motion. difference between Lagrangian and Newton-Euler formulation, derivation of dynamics equation using formulations, use of equations, required amount of computation, identification method for inertial parameters of manipulators
    
4. Manipulability - evaluating quantitatively ability of manipulators to easily arbitrarily change position and orientation of end effector at tip of manipulator, from the viewpoints of kinematics and dynamics. Not included: size of workspace, positioning accuracy, load capacity, speed, reliability, safety, cost, ease of operation, and settling time
    
5. Position Control - control algos and construction of control systems, methods for determining desired trajectory through given points
    
6. Force Control - ways to control force exerted by robot to objects, types of force control: impedance control (adjust stiffness against force of end effector vs external orces), hybrid control (two feedback loops for separate control of position and force)
    
7. Control of Redundant Manipulators - manipulator has redundancy if it has more degrees of freedom than are necessary to perform a given task, advantages disadvantages of redundant manipulators, method for actively utilizing redundancy to avoid obstacles and singular configurations (?)
    

  

### Spong, Mark W., and Mathukumalli Vidyasagar 2004. Robot dynamics and control

*

1. Introduction - history, components and structure of robots, outline of the text. Included: kinematics, dynamics, motion planning, computer vision, and control, Not included: locomotion, grasping, AI, computer architectures, programming languages, computer-aided design
    
2. Rigid Motions and Homogeneous Transformations - rigid - unable to bend or be forced out of shape, homogeneous transformation - combines rotation and translation into a single matrix multiplication, represent points and vectors in Euclidean space with coordinate frames, rotation matrix
    
3. Forward Kinematics: The Denavit-Hartenberg Convention - relationship between the individual joints of the robot manipulator and the position and orientation of the tool or end-effector
    
4. Inverse Kinematics - determining values for the joint variables that achieve a desired position and orientation for the end-effector
    
5. Velocity Kinematics -- The Manipulator Jacobian - velocity relationships of (1) linear and angular velocities of end-effector, and (2) joint velocities; uses of Jacobian matrix in robotic manipulation (ex: planning and execution of smooth trajectories, execution of coordinated anthropomorphic motion)
    

1. Singular Configurations - manipulator loses one or more degrees of freedom
    

7. Computer Vision
    

1. Geometry of Image Formation - geometric relationship between objects in the world and their projections in an image
    
2. Camera Calibration - calibrating camera to match image pixel coordinate to coordinate in the real world
    
3. Segmentation by Thresholding - separate objects from backgrounds by setting threshold on gray-ness of pixel values
    
4. Component labelling - differentiating objects based on adjacent pixels (if it’s disconnected/not adjacent, means it’s a different object)
    
5. Position and Orientation - compute position and orientation in industrial applications, i.e. depth (distance to object) is fixed
    

9. Path Planning and Collision Avoidance - configuration space, artificial potential fields, random motions to escape local minima, probabilistic roadmap method
    
10. Trajectory Planning - what should be the joint velocities and accelerations while traversing the path, chapter seems incomplete and looks like a draft??
    
11. Dynamics - describe the relationship between force and motion (vs kinematics describe motion without considering forces that produce the motion), Euler-Lagrange equations, holonomic constraints, Principle of Virtual Work, Lagrangian of the system, Newton-Euler formulation
    
12. Independent Joint Control - techniques to derive a control law for each joint of a manipulator based on a single-input/single-output model
    
13. Multivariable Control - control problem in context of whole system of joints
    
14. Force Control - strategies for controlling force of end-effector to objects
    
15. Feedback Linearization - construct a nonlinear control law that exactly linearizes the nonlinear system after a suitable state space change of coordinates
    

  
  

Craig 2005 Intro to robotics

  

### Lynch, K.M. and Park, F.C., 2017. Modern Robotics. 

- touches on many topics and is approachable

1. Preview
    
2. Configuration Space - a specification of the positions of all points of the robot
    
3. Rigid-Body Motions
    
4. Forward Kinematics
    
5. Velocity Kinematics and Statics - statics - analysis of loads acting on physical systems that do not experience an acceleration
    
6. Inverse Kinematics
    
7. Kinematics of Closed Chains - Any kinematic chain that contains one or more loops,  focused on parallel mechanisms (consisting of fixed and moving platforms connected by a set of “legs”)
    
8. Dynamics of Open Chains - study of motion taking into account forces and torques that cause them
    
9. Trajectory Generation - robot position as a function of time, time scaling (specifies the time when those configurations are reached)
    
10. Motion Planning - problem of finding a robot motion from a start state to a goal state that avoids obstacles in the environment and satisfies other constraints, such as joint limits or torque limits
    
11. Robot Control - motion control, force control, hybrid motion-force control, or impedance control
    
12. Grasping and Manipulation - contact kinematics; contact force modelling; and the dynamics of rigid bodies
    
13. Wheeled Mobile Robots - kinematic model of a mobile robot governs how wheel speeds map to robot velocities  
      
    

Specialized  
  
Tsai, L.W., 1999. Robot analysis: the mechanics of serial and parallel manipulators. - very thorough on kinematics


### Ogata 2010. Modern Control Engineering 

*- concerned with modelling, analysis and design of control systems important for robotic systems

1. Introduction to Control Systems
    
2. Mathematical Modeling of Control Systems
    
3. Mathematical Modeling of Mechanical Systems and Electrical Systems
    
4. Mathematical Modeling of Fluid Systems and Thermal Systems
    
5. Transient and Steady-State Response Analyses
    
6. Control Systems Analysis and Design by the Root-Locus Method
    
7. Control Systems Analysis and Design by the Frequency-Response Method
    
8. PID Controllers and Modified PID Controllers
    
9. Control Systems Analysis in State Space
    
10. Control Systems Design in State Space
    



Siciliano, B., Sciavicco, L., Villani, L. and Oriolo, G., 2010. Robotics: modelling, planning and control

