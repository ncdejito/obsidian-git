[[Automate development (DevOps)]]

### Routines

* Insert line to bashrc
```
echo "export PATH=\"/root/.local/bin:$PATH\"" >> ~/.bashrc
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
* [unzip tar.gz file](https://www.tutorialrepublic.com/faq/how-to-extract-a-tar-gz-file-using-command-line-in-ubuntu.php)
```
tar -zxvf file.tar.gz
```
* detach using ctrl+a d

* log to file
```
command >> logfile.log # append
command > logfile.log # overwrite
```
* string replace
```
sed 's/unix/linux/g' geekfile.txt
```
* run in background
```
command &
```

* delete all files inside a folder except a few files
```
rm -v !("filename1"|"filename2")
```
* check architecture i.e. arm64, amd64
```
uname -a
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
ps -v
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
* delete apt repo
```
sudo add-apt-repository --remove https://ppa.hub.org
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

## Info on OS
```
uname -a
```
## Concepts
How do processes work? Why cant I access processes inside a screen?

## Errors
#fix sudo apt update results in >> E: Failed to fetch http://ph.archive.ubuntu.com/ubuntu/dists/focal/InRelease 403 Forbidden
Solution: https://askubuntu.com/a/192388

## References
[Expert-level linux commands](https://peterlyons.com/leveling-up/)
Log parsing commands like sed grep [linkedin](https://www.linkedin.com/posts/sahnlam_log-parsing-commands-are-very-useful-activity-7037304369268101120-0fsU?utm_source=share&utm_medium=member_desktop)
