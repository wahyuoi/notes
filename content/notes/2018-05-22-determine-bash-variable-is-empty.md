---
title: Determine Bash Variable is Empty
date: 2018-05-22T15:45:10.577Z
type: til
---
Determine If Variable is Empty
---

`if [ -z "$VAR" ];`

will return true if $VAR is unset or set to empty string
