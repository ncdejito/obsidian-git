[[DevOps]]

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
* enter running image
```
docker exec -it 7b43e08f6350 /bin/bash
```
* copy a file from a container to the host 
```
docker cp <containerId>:/file/path/within/container /host/path/target
```

* build from dockerfile
```
docker build -t image:latest .
```
* retag
```
docker tag backend:latest backend:local
```

### Best practices

* [Don't use Docker for ROS, does not provide interfaces to low-level hardware, use Snapcraft](https://ubuntu.com/blog/ros-docker)
* [Running --privileged on docker is insecure](https://www.trendmicro.com/en_us/research/19/l/why-running-a-privileged-container-in-docker-is-a-bad-idea.html)
* [Pin docker image by using a digest](https://docs.docker.com/engine/reference/commandline/pull/#pull-an-image-by-digest-immutable-identifier) - SHA code when image is pulled to make sure you pull the same image every time, code is shown when you pull it the first time
e.g.
```
docker pull osrf/ros:humble-desktop-full
docker pull osrf/ros@sha256:6f719213030a8823179152d2caa4b39093bd3ae71b8f6b885413abff3536cd18

# List digests in local images
docker images --digests
```
* When developing use Dockerfiles to record commands ran, to ensure replicability later - Isaac Wilder

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


## WSL

20220728

Done:
x Fix docker wsl2 not found  
x try docker ros on windows
Next steps:
Stick with ubuntu for dev

#fix The command 'docker' could not be found in this WSL 2 distro.
We recommend to activate the WSL integration in Docker Desktop settings.
1. open Docker first, wait for it to get to "Running"
1. Settings > Resources > WSL Integration > Disable Ubuntu > Apply and Restart
1. Enable Ubuntu > Apply and Restart
1. open VSCode + WSL
1. docker should now work

Access WSL 2 folder on Windows Explorer
```
\\wsl$\Ubuntu
```





open image and bash
docker run -it --entrypoint /bin/bash osrf/ros
docker run -it --entrypoint /bin/bash ros:humble
source /opt/ros/humble/setup.bash
sudo apt update

sudo apt install vim
sudo apt install tmux

saving
docker ps # separate terminal
docker commit 7060929325fa ros:workspace

docker run -it --entrypoint /bin/bash ros:workspace

sudo apt install ros-humble-desktop


https://navigation.ros.org/getting_started/index.html

#fix Cannot connect to the Docker daemon at unix:///var/run/docker.sock. Is the docker daemon running?
1. Settings > Resources > WSL Integration > Disable Ubuntu > Apply and Restart
1. Enable Ubuntu > Apply and Restart

#fix permisison denied
```
sudo groupadd docker
sudo usermod -aG docker $USER
```