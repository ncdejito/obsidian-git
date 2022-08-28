### Routines
* empty file in vi

```
:1,$d
```
* Empty linux recycle bin

```
cd ~/.local/share/Trash/files
rm -rf *
```
* zip a folder

```
zip -r archivename.zip directory_name
```
* unzip to a folder

```
unzip -d landuse landuse.zip
```

* unzip a 7z

```
sudo apt install p7zip
7z x /content/TH.2020.2021.wdwe-4h.csv.7z
```
* unzip an xz file
```
sudo apt install p7zip-full

```

* start screen session named jl

```
screen -S jl
```

* detach using ctrl+a d

* reattach to screen

```
screen -ls
screen -r 10835
```

Make bashes have env variables based on .env in current dir
```
sudo apt install direnv
vim ~/.bashrc
eval "$(direnv hook bash)"
cd dir
direnv allow
```

## Install Flatpak
```
flatpak remote-add --if-not-exists flathub https://flathub.org/apps/details/org.winehq.Wine
flatpak install flathub org.winehq.Wine

```

## Run windows programs
```
flatpak run org.winehq.Wine RoboStudio/robostudio.exe
```