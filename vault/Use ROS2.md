

## Gists
```
colcon build --symlink-install
source install/setup.bash
```
[[Colcon]] notes
```
source /opt/ros/galactic/setup.bash
```

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

Location of ROS2 scripts
```
cd /opt/ros/galactic/share
ls turtlebot3_bringup
```

```
ros2 topic info -v /topic

ros2 param set slam_toolbox max_laser_range 3.5

export ROS_DOMAIN_ID=0
echo "export ROS_DOMAIN_ID=0" >> ~/.bashrc

```

Switch to CycloneDDS
```
sudo apt install ros-humble-rmw-cyclonedds-cpp
export RMW_IMPLEMENTATION=rmw_cyclonedds_cpp
ros2 launch two_wheeled_robot office_world_v1.launch.py >> office_world_v1_launch.log &
```

Activate python
```
python3
```

Searching binaries for launch files
```
ls /opt/ros/galactic/share/rplidar_ros/launch
```
## Introspection
[[tf2]]
View node graph - `rqt`

## Concepts
Node - e.g. motor controller, laser range finder
- Subscribers - node listens to these topics (following)
	- Topic1
		- msg/ - format of data to read and be read by other nodes in the system
- Publishers - node publishes to these topics (feeds posted to like IG/FB feed)
	- Topic1
- Services - send request and wait for response
	- Server - this node sends responses to requests from other nodes
	- Client - this node sends request to other nodes
- Action - long running tasks, can be async
	- Server
		- Goal Service Server - responds to goals
		- Feedback Publisher - sends feedback to topic
		- Results Service Server
	- Client
		- Goal Service Client - sends goals
		- Feedback Subscriber
		- Results Service Client
- Parameters - variables with values inside a node (like [[Use Python]] class)

```
$ ros2 service list -t
/service [service-type]
$ ros2 interface show <service-type>
structure of request
---
structure of response
```

```
$ ros2 action list -t
/action [action-type]
$ ros2 interface show <action-type>
structure of goal request
---
structure of result request
---
structure of feedback
```


## Next generation
* Ros2 on microk8s
* Rxros - Functional, reactive
* vulcanexus all in one ros2
* Prometheus export ros discourse
* Microros - use ros2 on microcontrollers
* Fogros2 - cloud robotics, run listener talker example aws local cloud?
* OpenRMF  multi-robot traffic management system [slides](https://docs.google.com/presentation/d/1Lt79xlM_XkITmURSbI5hkAAgnjSX8dHKBkgvz3x3Uzw/edit)

## Gotchas
* if you close a docker terminal, the process running there is still running on your docker image
