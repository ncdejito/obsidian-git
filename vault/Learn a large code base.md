[[Use Nav2]]
[[Automate development (DevOps)]]

Fastest way is to fix bugs
- unknown which part is causing problems so you have to read up on the codebase
- youd need to understand critical paths on how things work

Find instances of pattern in a folder of files
```
grep --exclude-dir=deploy -r -n -B1 -A1 PATTERN *

grep --exclude=deploy --exclude=*log.txt --exclude=log* -r -I -n -B1 -A1 SUBSYSTEM_LN *
grep void -r --include=\*.cpp --include=\*.h
```

Search bar in Vscode - replacement for grep

Study repositories with chatgpt  
[https://useadrenaline.com/app](https://useadrenaline.com/app)

Chat with your codebase
https://github.com/rsaryev/talk-codebase

Search function names in natural language, without pushing data to the internet
https://github.com/sturdy-dev/semantic-code-search

When working on a large monolithic codebase, measuring codebase familiarity can be challenging. However, there are some tried and tested frameworks that can help. 
1. One approach is to start by finding and reading the code paths that perform some recognizable action. 
2. Running tests and reading them can also be helpful. 
3. Another approach is to add a new feature with tests or pick an open issue and try to fix it. 
It's important to remember that you don't need to familiarize yourself with the full codebase at the start. Instead, set up an objective and go for it, slashing your coding axe around until it works. Additionally, installing useful plugins in your IDE can help you navigate your codebase and notice problems more quickly. Finally, tracking metrics such as cyclomatic complexity, code length, and code churn can help you improve cognitive complexity and better understand the codebase over time

Get scripts with top git activity
```
export FOLDER=src/subfolder1

git log --pretty=format: --name-only --since "DEC 31 2021" -- ${FOLDER} | sort | uniq -c | sort -rg # get scripts with top activity
```