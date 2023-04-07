[[Connect computers with Networking]]

Add linux device to your network
```
sudo snap install zerotier
sudo zerotier-cli info
snap connect zerotier:network-control
sudo zerotier-cli join abcdefg123456 # zerotier network ID
# in my.zerotier.com, check Auth
# address to ssh to is now in managed IPs
```