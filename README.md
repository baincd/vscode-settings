# Chris' VS Code Setup

## How to setup

Open a bash or Git Bash terminal, and cd to the [VS Code user settings location](https://code.visualstudio.com/docs/getstarted/settings#_settings-file-locations).  Then run the following commands:

1. Backup existing files
2. Clone repo and checkout Files
3. Open VS Code workspace, display extensions to install

```bash
TMPDIR=BKUP_`date +%Y-%m-%d_%H%M%S` && mkdir -p $TMPDIR && find -maxdepth 1 -regextype posix-extended -regex "\./(settings.json|keybindings.json|tasks.json|.vscode|snippets)" -exec mv -v {} $TMPDIR \;

git init && git remote add origin https://github.com/baincd/vscode-settings.git && git fetch --all && git checkout -t origin/main

code -n VS\ Code\ Settings.code-workspace extensions.md

```
