# Remote Git repositories

## Adding and inspecting a remote

A remote is a saved name for another repository location. `origin` is the conventional name for the primary remote; it is a name, not a special Git command.

```bash
git remote add origin https://github.com/abuammer-051/git-repositories-homework.git
git remote -v
```

Older examples often use a branch named `master`, as in `origin/master`. This repository uses the modern default name `main`, so its remote-tracking branch is `origin/main`.

## Push and upstream

`push` sends local commits to a remote. The `-u` option also records the relationship between the local branch and its remote-tracking branch:

```bash
git push -u origin main
```

After that first push, plain `git push` and `git pull` normally know which remote branch to use. The relationship can be inspected with:

```bash
git branch -vv
```

An equivalent explicit upstream command is:

```bash
git branch --set-upstream-to=origin/main main
```

## Fetch compared with pull

```bash
git fetch origin
git pull --ff-only origin main
```

- `git fetch` downloads remote objects and updates remote-tracking references, but it does not integrate them into the checked-out branch.
- `git pull` fetches and then integrates the selected remote branch. `--ff-only` is a cautious option that refuses to create an unexpected merge commit.

It is often useful to fetch first, inspect the difference, and then decide how to integrate it:

```bash
git fetch origin
git log --oneline main..origin/main
git diff main..origin/main
git merge --ff-only origin/main
```

## Clone

`clone` creates a new local repository from a remote, downloads its history, checks out a working copy, and normally configures the source as `origin`:

```bash
git clone https://github.com/abuammer-051/git-repositories-homework.git
cd git-repositories-homework
git remote -v
git status
```

## Practical workflow used for this assignment

```bash
git init -b main
git add .
git commit -m "chore: initialize Git homework repository"
git remote add origin <repository-url>
git push -u origin main
git fetch origin
git pull --ff-only
git clone <repository-url>
```

The public GitHub repository and a fresh clone are verified at the end of the exercise.
