[[Workspace]]

1. Install Remote - WSL extension

Update VSCode
`sudo dpkg -i code.deb`

## Config

[[Python]]
```
// settings.json
    "python.formatting.blackArgs": [
        "--line-length",
        "80"
    ],
```

Run selected text in terminal
- Settings > Command Palette > Run Selected Text in Active Terminal

## Errors
#fix [[Git]] no anonymous write access
Source of error is VSCode CLI authentication
[instructions](https://stackoverflow.com/a/70035832)