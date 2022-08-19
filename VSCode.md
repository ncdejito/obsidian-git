[[Workspace]]

1. Install Remote - WSL extension

Update VSCode
`sudo dpkg -i code.deb`

[[Python]]
```
// settings.json
    "python.formatting.blackArgs": [
        "--line-length",
        "80"
    ],
```

#fix [[Git]] no anonymous write access
Source of error is VSCode CLI authentication
[instructions](https://stackoverflow.com/questions/60757334/git-push-from-visual-studio-code-no-anonymous-write-access-authentication-fai)