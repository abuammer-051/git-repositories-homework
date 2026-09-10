# Local Git repositories

## Repository setup

A Git repository is a project directory whose changes are tracked in a hidden `.git` directory. A new repository can be created and given `main` as its first branch with:

```bash
mkdir git-repositories-homework
cd git-repositories-homework
git init -b main
```

Git records the author name and email in each commit. They can be configured with `git config --global user.name` and `git config --global user.email`, then checked with `git config --list`.

## The three working areas

```text
Working directory  --git add-->  Staging area  --git commit-->  Repository history
```

- **Working directory:** the files currently being edited.
- **Staging area:** the exact changes selected for the next commit.
- **Repository:** the permanent sequence of commits stored by Git.

## Common file states

- **Untracked:** Git sees a new file that has never been committed.
- **Staged:** the file's current contents have been added to the staging area.
- **Unmodified:** the working copy matches the latest committed version.
- **Modified:** a tracked file differs from the latest committed version.

`git status` reports these states. `git status --short` gives a compact two-column view. For example, `??` means untracked, `A` means added to the index, and `M` means modified.

## Saving a file in Git

Create or edit a file, inspect it, stage it, and commit it:

```bash
git status
git add examples/hello.txt
git status
git commit -m "docs: add file-state example"
git status
```

`git add` does not permanently save a version by itself; it prepares the selected snapshot. `git commit` records that staged snapshot in the repository's history.

## Reviewing work

```bash
git diff                 # unstaged changes
git diff --staged        # staged changes
git log --oneline        # concise history
```

Clear commit messages make the history understandable. It is better to commit one logical change at a time than to combine unrelated work.
