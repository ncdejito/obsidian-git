short range but accurate

An introduction to LIDAR by Oliver Cameron
https://news.voyage.auto/an-introduction-to-lidar-the-key-self-driving-car-sensor-a7e405590cff

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

Lidar datasets - for openPCL experiments?
https://robotki.github.io/datasets.html

Global lidar localization survey
https://www.linkedin.com/posts/cyrill-stachniss-736233173_lidar-localization-mobilerobotics-activity-7176080012326924288-jpYw?utm_source=share&utm_medium=member_android

Camera vs lidar comparison
https://www.linkedin.com/posts/peter-soetens_is-anyone-believing-that-when-cameras-dont-activity-7257047284922642433-MtN_

#fix Cannot start scan: '80008002'
Remove then reconnect wire