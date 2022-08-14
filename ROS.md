[[Robotics]] [[Workspace]]  

```
# # added to local machine ~/.bashrc
# export DISPLAY=:0.0
# xhost +local:docker

# saved to local machine as alias ros=''
# docker run -it --net=host --device /dev/dri/ -e DISPLAY=$DISPLAY -v $HOME/.Xauthority:/root/.Xauthority:ro a:workspace
ros

# # environment setup - added to docker image ~/.bashrc
# source /opt/ros/humble/setup.bash
# export TURTLEBOT3_MODEL=waffle
# export GAZEBO_MODEL_PATH=$GAZEBO_MODEL_PATH:/opt/ros/humble/share/turtlebot3_gazebo/models


# run example
ros2 launch nav2_bringup tb3_simulation_launch.py headless:=False

docker ps
docker commit 2994909db49c a:workspace
```
