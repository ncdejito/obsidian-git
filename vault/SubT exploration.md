# SubT exploration

hello world code doesnt run anymore after my modifications to base
[[Hardware]]

[[Docker]] commands
```
# open image and bash 
docker run -it --entrypoint /bin/bash -v /dev/input:/dev/input --privileged osrf/subt-virtual-testbed:latest 

# open simulation 
./subt/docker/run.bash osrf/subt-virtual-testbed competition.ign worldName:=simple_cave_01 circuit:=cave robotName1:=X1 robotConfig1:=X1_SENSOR_CONFIG_1 

# connect controls to existing 
docker ps 
docker exec -it 64eed3979516 /bin/bash sudo apt-get update && sudo apt-get install ros-melodic-teleop-twist-keyboard rosrun teleop_twist_keyboard teleop_twist_keyboard.py /cmd_vel:=/X1/cmd_vel 

# saving 
docker ps 
# separate terminal 
docker commit 52a9200a3ad8 osrf/subt-virtual-testbed:latest
```

