[[DevOps]]

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

* detach using ctrl+a d

* log to file
```
command >> logfile.log
```
* run in background
```
command &
```

* delete all files inside a folder except a few files
```
rm -v !("filename1"|"filename2")
```

Make bashes have env variables based on .env in current dir
```
sudo apt install direnv
vim ~/.bashrc
eval "$(direnv hook bash)"
cd dir
direnv allow
```


## Processes
* List processes
```
ps
```
* Kill process
```
kill -9 processIDakaPID
```
* check process output
```
tail -f /proc/<pid>/fd/1
# `1` = stdout, `2` = stderr
```


* start screen session named jl

```
screen -S jl
```
* reattach to screen

```
screen -ls
screen -r 10835
```

* kill screen
```
screen -X -S [session # you want to kill] quit
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

## Concepts
How do processes work? Why cant I access processes inside a screen?

## Errors
#fix sudo apt update results in >> E: Failed to fetch http://ph.archive.ubuntu.com/ubuntu/dists/focal/InRelease 403 Forbidden
Solution: https://askubuntu.com/a/192388

## References
[Expert-level linux commands](https://peterlyons.com/leveling-up/)