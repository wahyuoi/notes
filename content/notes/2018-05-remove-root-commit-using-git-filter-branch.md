---
title: Remove root commit using git filter-branch
date: 2018-05-17T10:34:58.319Z
tags: ["til"]
---
How to :
- find out commit ID of the root
- use git filter-branch using --parent-filter and a sed command that snips off that parent. `git filter-branch --parent-filter "sed 's/-p <the_commit>//'" HEAD`

Notes:
all files on old root commit will be moved to new root commit.


Source: https://stackoverflow.com/questions/6149520/git-remove-root-commit
