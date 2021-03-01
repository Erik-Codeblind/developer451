---
title: "Git Bulk Delete Branches Example"
date: 2021-03-01T11:38:01-05:00
summary: "How to delete all git branches matching a given pattern."
draft: true
---

In this example we want to delete all branches from our local git repo that begin with `fix/`.


1. Identify all branches in a github repo that start with `fix/`.

```shell
git branch --list "fix/*"
```

You will see list of branches matching the glob pattern, similar to this,
```shell
  fix/debug-console-error
  fix/dropcase-first-letter
  fix/font-size
  fix/off-by-one
  ```

2. If this list of files looks right, you can delete them all by piping the list to `xargs`.

```shell
git branch --list "fix/*" | xargs git branch -d
```

You might see some errors like these:

```shell
error: The branch 'fix/off-by-one' is not fully merged.
If you are sure you want to delete it, run 'git branch -D fix/off-by-one'.
```

These errors are a warning to let you know that your "main" branch (or the currently checked out branch) does not have all commits from the `fix/off-by-one` branch you are trying to delete. If you delete the branch, you will lose those changes and any history associated with them. If that is fine, you can run `xargs` again, this time passing the `-D` flag to `git`.

```shell
git branch --list "fix/*" | xargs git branch -D
```

3. Listing the branches beginning with `fix/` should no longer return any results.

```shell
git branch --list "fix/*"
```