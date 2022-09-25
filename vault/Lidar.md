[[Hardware]]

https://github.com/babakhani/rplidar_ros2

```
## connect to usb
docker run -it --net=host --device /dev/dri/ --device /dev/ttyUSB0 -e DISPLAY=$DISPLAY -v $HOME/.Xauthority:/root/.Xauthority:ro rplidar:latest

/dev/ttyUSB0

Bus 003 Device 007: ID 10c4:ea60 Silicon Labs CP210x UART Bridge
```