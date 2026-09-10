# Evidence: remote workflow

A temporary local bare repository was used as a safe practice remote before GitHub publication. The same Git commands and reference behavior apply to a hosted remote.

## Add and inspect `origin`

```text
$ git remote add origin Z:\git-homework-remote.git
$ git remote -v
origin  Z:\git-homework-remote.git (fetch)
origin  Z:\git-homework-remote.git (push)
```

## Push and set upstream

```text
$ git push -u origin main
* [new branch] main -> main
branch 'main' set up to track 'origin/main'.

$ git branch -vv
* main bb98c22 [origin/main] docs: explain remote repository workflow
```

## Clone and push from the clone

```text
$ git clone Z:\git-homework-remote.git Z:\git-homework-clone
$ git switch main
branch 'main' set up to track 'origin/main'.

$ git push
bb98c22..9e71bdf  main -> main
```

The commit `9e71bdf` added `evidence/clone-verification.md` from the separate clone.

## Fetch, inspect, and pull

Back in the original repository:

```text
$ git fetch origin
bb98c22..9e71bdf  main -> origin/main

$ git status --short --branch
## main...origin/main [behind 1]

$ git log --oneline main..origin/main
9e71bdf docs: record clone verification

$ git pull --ff-only
Updating bb98c22..9e71bdf
Fast-forward
```

This shows the difference between fetching remote references and pulling the remote commit into the current local branch.

## Publish to GitHub

The temporary practice remote was retained under a descriptive name, and the public GitHub repository became the primary `origin`:

```text
$ git remote rename origin practice
$ git remote add origin https://github.com/abuammer-051/git-repositories-homework.git
$ git push -u origin main
* [new branch] main -> main
branch 'main' set up to track 'origin/main'.
```

The final repository was then cloned from its public HTTPS URL and checked for a clean working tree and matching commit history.
