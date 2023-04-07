

### Software
Note taking
* Tasks -> Google Keep
* Plans -> Google Docs
* Long term memory -> Obsidian

Things to try
* Emacs Doom
* [Virtual Coworking](https://www.focusmate.com/)

Dual Booting
Ubuntu 18 and Windows 10 [blog](https://hackernoon.com/installing-ubuntu-18-04-along-with-windows-10-dual-boot-installation-for-deep-learning-f4cd91b58557)

Laptop Setup

Download
Chrome

[[VSCode]]
1. Install Remote - WSL extension

WSL
1. Open Control Panel, then go to Programs and select Turn Windows features on or off, scroll down to Windows Subsystem for Linux, select it and click the Ok button. Wait until the wizard end.
1. restart
1. Set version to WSL2
```
wsl --set-default-version 2
wsl --set-version Ubuntu 2
```
1. Microsoft Store, search "Ubuntu"
1. Get then install
1. 
```
vim ~/.bashrc
cd /mnt/c/Users/ncdej/Downloads
```
1. Enable ctrl+alt+arrow rotation: Intel Graphics Control Panel > Disable hotkeys for screen rotation


[[Use Docker]]
Install wsl2 kernel update
Settings > Resources > WSL Integration > Enable "Ubuntu"

NVIDIA Driver
https://www.acer.com/ac/en/ID/content/support-product/4281;-;
From official Acer website > VGA Driver > NVIDIA GeForce 640M LE

ROS2
just use docker image

Jupyter Lab
```
pip install jupyterlab
```

[Increase Virtual Memory](https://thegeekpage.com/increase-ram/) - 1.5 * 1024 * Installed RAM


#fix no grub dual boot menu after windows update
1. plug and boot to Ubuntu USB
1. click "Try Ubuntu"
1. install and run [Boot Repair](https://help.ubuntu.com/community/Boot-Repair)

#fix [Unexpected inconsistency run fsck manually](https://askubuntu.com/questions/697190/fsck-error-on-boot-dev-sda6-unexpected-inconsistency-run-fsck-manually)
run `fsck /dev/sda8`