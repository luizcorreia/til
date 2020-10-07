## Improve Git Log

By running the following from the command line, you can create a new Git command (`git lg`).

```bash
git config --global alias.lg "log --color --graph --date=format:'%Y-%m-%d %H:%M:%S' --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%ad) %C(bold blue)<%an>%Creset'"
```

This new command creates a much more useful log of Git commits.

