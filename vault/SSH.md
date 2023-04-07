[[Connect computers with Networking]]

Tested on Ubuntu MATE Jammy
```
sudo apt update --fix-missing
sudo apt install openssh-server
sudo apt update --fix-missing
sudo apt install sshguard
sudo systemctl enable ssh
sudo systemctl start ssh
```