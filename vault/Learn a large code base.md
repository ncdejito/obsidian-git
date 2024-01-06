[[Use Nav2]]
[[Automate development (DevOps)]]

Find instances of pattern in a folder of files
```
grep --exclude-dir=deploy -r -n -B1 -A1 PATTERN *

grep --exclude=deploy --exclude=*log.txt --exclude=log* -r -I -n -B1 -A1 SUBSYSTEM_LN *
grep void -r --include=\*.cpp --include=\*.h
```

Search bar in Vscode - replacement for grep

try [semgrep](https://semgrep.dev/)

Study repositories with chatgpt  
[https://useadrenaline.com/app](https://useadrenaline.com/app)

Chat with your codebase
https://github.com/rsaryev/talk-codebase

Search function names in natural language, without pushing data to the internet
https://github.com/sturdy-dev/semantic-code-search