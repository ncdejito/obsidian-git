[[URDF]]

```
xacro model.xacro > model.urdf
```
Xacro  
Why  
Work easier with URDF  
Be able to use VCS like git  

What  
Split files into multiple files  
Dont repeat yourself  
  
How (diagram from Articulated Robotics)
Add a xacro tag to urdf to use it  
Pass xml to xacro,  
xacro pushes to robot state publisher,  
robot state publisher sends to robot description topic

[xmacro](https://github.com/gezp/xmacro) - ros2-igt used sdf urdf parsing