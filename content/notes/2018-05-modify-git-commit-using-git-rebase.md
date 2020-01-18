---
title: Modify Git Commit Using Git Rebase
date: 2018-05-17T10:33:58.803Z
tags: ["til"]
---
To edit commit message, reorder commit, delete commit or squash commit, we can use `git rebase -i` or `git rebase --interactive` then change first word to any command that provided by git.

use `--root` to include root commit

List commands:

* p, pick = use commit
* r, reword = use commit, but edit the commit message
* e, edit = use commit, but stop for amending
* s, squash = use commit, but meld into previous commit
* f, fixup = like "squash", but discard this commit's log message
* x, exec = run command (the rest of the line) using shell

Reference: man git rebase
