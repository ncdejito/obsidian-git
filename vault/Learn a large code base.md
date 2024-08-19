* [[Trace the critical path]] of a recognizable action
* Insert print statements to check your understanding, especially in [[Distributed systems]]
* Fix bugs
* Read tests

Fastest way is to fix bugs
- unknown which part is causing problems so you have to read up on the codebase
- youd need to understand critical paths on how things work

Tools
Find instances of pattern in a folder of files
```
grep --exclude-dir=deploy -r -n -B1 -A1 PATTERN *

grep --exclude=deploy --exclude=*log.txt --exclude=log* -r -I -n -B1 -A1 SUBSYSTEM_LN *
grep void -r --include=\*.cpp --include=\*.h
```

Get scripts with top git activity
```
export FOLDER=src/subfolder1

git log --pretty=format: --name-only --since "DEC 31 2021" -- ${FOLDER} | sort | uniq -c | sort -rg # get scripts with top activity
```

Search bar in Vscode - replacement for grep

Chat with a github repo with llama3.1
https://www.linkedin.com/posts/eric-vyacheslav-156273169_game-changer-you-can-now-create-a-chatbot-activity-7226604741261230081-Bthf?utm_source=share&utm_medium=member_android