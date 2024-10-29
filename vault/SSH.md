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

#fix
ssh password change required but no tty available
solution: ssh normal from ubuntu terminal, will auto redirect to change password. then login again