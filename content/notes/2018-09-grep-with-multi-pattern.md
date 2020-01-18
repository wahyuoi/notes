---
title: Grep with Multi Pattern
date: 2018-09-10T10:37:21.317Z
tags: ["til"]
---
mostly we use grep to find single word/pattern. 
when we need to find multi patterns in single command, use `-E` options and use pipe as delimiter for patterns

example:

`grep -E 'pattern1|pattern2'`
