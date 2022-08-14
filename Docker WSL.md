
[[Docker]]

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

