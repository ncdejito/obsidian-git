[[Use Nav2]]
[[Automate development (DevOps)]]

Find instances of pattern in a folder of files
```
grep --exclude-dir=deploy -r -n -B1 -A1 PATTERN *

grep --exclude=deploy --exclude=*log.txt --exclude=newlog* -r -I -n -B1 -A1 SUBSYSTEM_LOCALISATION *
grep void -r --include=\*.cpp --include=\*.h
```

Search bar in Vscode - replacement for grep

try [semgrep](https://semgrep.dev/)

Study repositories with chatgpt  
[https://useadrenaline.com/app](https://useadrenaline.com/app)