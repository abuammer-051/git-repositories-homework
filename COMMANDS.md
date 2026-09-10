# Git command reference

| Goal | Command |
| --- | --- |
| Create a repository with `main` | `git init -b main` |
| Show file and branch state | `git status` |
| Show compact file state | `git status --short` |
| Stage one file | `git add <file>` |
| Stage all current changes | `git add .` |
| Record the staged snapshot | `git commit -m "message"` |
| View concise history | `git log --oneline --graph --decorate --all` |
| Add the primary remote | `git remote add origin <url>` |
| List configured remotes | `git remote -v` |
| Push and set upstream | `git push -u origin main` |
| Download remote changes only | `git fetch origin` |
| Download and integrate changes | `git pull --ff-only` |
| Inspect upstream relationships | `git branch -vv` |
| Clone a repository | `git clone <url>` |

Angle-bracket values such as `<file>` and `<url>` are placeholders and should be replaced with real values.
