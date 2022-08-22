
### Routines 
* open image and bash
```
docker run -it --entrypoint /bin/bash image:tag
```
-v /dev/input:/dev/input --privileged osrf/subt-virtual-testbed:latest
* saving
```
docker ps # separate terminal

docker commit 52a9200a3ad8 osrf/subt-virtual-testbed:latest
```


### Best practices

* [Don't use Docker for ROS, does not provide interfaces to low-level hardware, use Snapcraft](https://ubuntu.com/blog/ros-docker)
* [Running --privileged on docker is insecure](https://www.trendmicro.com/en_us/research/19/l/why-running-a-privileged-container-in-docker-is-a-bad-idea.html)
* [Pin docker image by using a digest](https://docs.docker.com/engine/reference/commandline/pull/#pull-an-image-by-digest-immutable-identifier) - SHA code when image is pulled to make sure you pull the same image every time, code is shown when you pull it the first time
e.g.
```
docker pull osrf/ros:humble-desktop-full
docker pull osrf/ros@sha256:6f719213030a8823179152d2caa4b39093bd3ae71b8f6b885413abff3536cd18
```


## VM
```
apt install vim
apt install wget
apt install python3
apt install python-is-python3

```

### Fixes
#fix qt.qpa.xcb: could not connect to display :0
run the ff:
```
export DISPLAY=:0.0
xhost +local:docker
```


