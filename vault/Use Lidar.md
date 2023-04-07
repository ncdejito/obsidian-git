

RPLidar 
Official Slamtec [code](https://github.com/Slamtec/rplidar_ros/tree/ros2)
fork [code](https://github.com/babakhani/rplidar_ros2) ver: Humble Hawksbill

```
apt install ros-galactic-rplidar-ros -y
```

```
## connect to usb
docker run -it --net=host --device /dev/dri/ --device /dev/ttyUSB0 -e DISPLAY=$DISPLAY -v $HOME/.Xauthority:/root/.Xauthority:ro rplidar:latest

/dev/ttyUSB0

Bus 003 Device 007: ID 10c4:ea60 Silicon Labs CP210x UART Bridge
```

```
ros2 launch rplidar_ros rplidar.launch.py
ros2 launch rplidar_ros view_rplidar.launch.py
```

Other LIDARs
linorobot bash [script](https://github.com/linorobot/linorobot2/blob/galactic/install_linorobot2.bash#L62)
rokr - turn 2d lidar to 3d



#fix Cannot start scan: '80008002'
Remove then reconnect wire