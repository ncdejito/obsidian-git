Connect to Wifi
[instructions](https://itsfoss.com/connect-wifi-terminal-ubuntu/)
location: /etc/netplan/00-snapd-config.yaml
```
network:
  ethernets: {}
  version: 2
  wifis:
    wlan0:
      access-points:
        HUAWEI-2.4G-72Gf_plus:
          password: VhN264s7
      dhcp4: true
```


Install docker as a snap
```
sudo snap install docker
```

Create and run docker image
```
sudoedit Dockerfile
#FROM python:3.8-slim
#RUN pip install pyfirmata

sudo docker build . -t pyfirmata:latest
sudo docker run -it --entrypoint /bin/bash --device /dev/ttyACM0 pyfirmata:latest
```

Test if it works
```
from pyfirmata import Arduino, util
board = Arduino('/dev/ttyACM0')

board.digital[13].write(1)
```

Run on a VM [blog](https://ubuntu.com/download/kvm)