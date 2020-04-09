# Use VS Code as your merge and difftool

```bash
[user]
  email = <your-email>
  name = <your-name>
[merge]
    tool = vscode
[mergetool "vscode"]
    cmd = code --wait $MERGED
[diff]
    tool = vscode
[difftool "vscode"]
    cmd = code --wait --diff $LOCAL $REMOTE
```
