[[Workspace]]  

Fix LibreOffice Calc dialog box upon open of csv files

```
# https://bugs.documentfoundation.org/show_bug.cgi?id=74580#c47

cat /etc/gnome/defaults.list
ls /usr/share/applications
cat /usr/share/applications/libreoffice-calc.desktop | grep -v '#' | head -n7

cp libreoffice-calc.desktop libreoffice-calc_csv.desktop
sudo vim /usr/share/applications/libreoffice-calc_csv.desktop
# replace: Exec=libreoffice --calc %U
# with: Exec=libreoffice --calc --infilter="Text - txt - csv (StarCalc)":44,34,0,1 %U

sudo vim /etc/gnome/defaults.list
# replace application/csv,text/commaseparated,text/csv default with _csv
```

rotate display
```
xrandr -o left
xrandr -o normal
```

#fix Need to run fsck manually
```
fsck /dev/sda8
```

#fix Pending update of snap-store 
[solution](https://askubuntu.com/a/1429871)
```
killall snap-store
sudo snap refresh
```