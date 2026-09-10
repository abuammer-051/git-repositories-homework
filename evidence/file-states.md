# Evidence: Git file states

The following experiment was performed in this repository.

## 1. Untracked

After `examples/hello.txt` was created, `git status --short` displayed:

```text
?? examples/hello.txt
```

## 2. Staged for its first commit

After `git add examples/hello.txt`, the status displayed:

```text
A  examples/hello.txt
```

## 3. Committed and unmodified

After the commit, `git status --short` produced no file entries. That clean result means the working tree matched the committed snapshot.

## 4. Modified

After another line was added to the tracked file, the status displayed:

```text
 M examples/hello.txt
```

The right-hand `M` means the working-directory copy was modified but not staged.

## 5. Modified and staged

After running `git add examples/hello.txt` again, the status displayed:

```text
M  examples/hello.txt
```

The left-hand `M` means the modification was staged for the next commit. This sequence demonstrates how the same file moves through Git's working directory, staging area, and repository history.
