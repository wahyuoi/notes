---
title: 'Vim: Reverse Lines'
date: 2018-05-20T10:36:18.317Z
tags: ["til"]
---
`:g/^/m0`

It will reverse all lines on file. If you want to reverse on specific lines, add line number before the command.

`:5,10g/^/m4`

It will reverse line 5 to 10 and put the result after line 4.
