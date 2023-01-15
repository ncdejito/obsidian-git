[[ROS2]]

Unified Robotics Description Format
describes shape and physics of parts of robot
links - components e.g. base, arm, lidar, camera
joints - connections of links e.g. base to arm, arm to lidar

Links - components of the robot  
Joints - relationship between links  
  
Type of joints  
Revolute - rating arm  
Continuous - wheels  
Prismatic - straight  
Fixed  
  
Link tags  
Name _link  
Visual - whats seen in gazebo or rviz  
-geometry - box sphere or 3d mesh  
-origin - coords  
-material - color  
Collision - for physics calculations  
-geometry  
-origin  
Inertial - how links responds to forces  
-mass - how heavy  
-origin - center of mass  
-inertia - rotational intertia ma how distribution of mass affects rotation of linkes, prisms ellipsoids  
  
Joint tags  
Name type _joint  
Parent  
Child  
Origin - relationship between 2 links when a motion is applied  
Axis - which axis joint moves around ir along like rotation  
Limits - rotation, velocity, effort  
  
Gazebo tags  
Actuator tags

Tutorials
Articulated Robotics [video](https://www.youtube.com/watch?v=BcjHyhV0kIs)
ROS2 Tutorial [page](https://docs.ros.org/en/humble/Tutorials/Intermediate/URDF/Building-a-Visual-Robot-Model-with-URDF-from-Scratch.html)
Python URDF maker [repo](https://github.com/hauptmech/odio_urdf)