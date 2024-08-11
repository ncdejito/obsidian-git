[[Use ROS2]]

creates a lookup table of poses using timestamp as key tf2.Buffer

View tf tree
```
sudo apt-get install ros-galactic-turtle-tf2-py ros-galactic-tf2-tools ros-galactic-tf-transformations

ros2 run tf2_tools view_frames
ros2 run tf2_ros tf2_echo base_link base_laser
```