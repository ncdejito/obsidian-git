[[Hardware]] [[Workspace]]  

## Gists
```
source /opt/ros/humble/setup.bash
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

```
ros2 topic info -v /topic

ros2 param set slam_toolbox max_laser_range 3.5
```

## Concepts
Node - e.g. motor controller, laser range finder
- Subscribers - node listens to these topics (following)
	- Topic1
		- msg/ - format of data to read and be read by other nodes in the system
- Publishers - node publishes to these topics (feeds posted to like IG/FB feed)
	- Topic1
- Services - send request and wait for response
	- Server - other nodes send request to this node
	- Client - this node sends request to other nodes
- Action - long running tasks, can be async
	- Server
	- Client

## Gotchas
* if you close a docker terminal, the process running there is still running on your docker image
