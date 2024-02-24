# Chris' VS Code Setup

## How to setup

Open a bash or Git Bash terminal, and cd to the [VS Code user settings location](https://code.visualstudio.com/docs/getstarted/settings#_settings-file-locations).  Then run the following commands:

```bash
# 1. Backup existing files
TMPDIR=BKUP_`date +%Y-%m-%d_%H%M%S` && mkdir -p $TMPDIR && find -maxdepth 1 -regextype posix-extended -regex "\./(settings.json|keybindings.json|tasks.json|.vscode|snippets)" -exec mv -v {} $TMPDIR \;

# 2. Clone repo and checkout Files
git init && git remote add origin https://github.com/baincd/vscode-settings.git && git fetch --all && git checkout -t origin/main

# 3. Open `VS Code Settings.code-workspace` in VS Code
code -n VS\ Code\ Settings.code-workspace
```

4. Install extensions
    - Open .vscode/extensions.json in VS Code Settings workspace
    - Uncomment extension for functionality that is wanted
    - Open the Extensions sidebar
    - Install recommended extensions

5. Restore backedup settings
    - Open BKUP_yyyy-mm-dd/* files
    - Copy to existing files
