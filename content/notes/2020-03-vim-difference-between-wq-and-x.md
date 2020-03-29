---
title: 'Vim: Difference between :wq and :x'
date: 2020-03-29T14:10:23.637Z
tag:
  - til
---
[How do I exit the Vim editor?](https://stackoverflow.com/questions/11828270/how-do-i-exit-the-vim-editor)

This question already asked years ago and still tricky for some engineers.

Few approaches on exiting vim that I know :

1. using :wq
2. using :x
3. close terminal (please don't)
4. turnoff the PC (please don't)

Today I learnt that :x and :wq are not the same thing! Both command will save and quit, but there is one difference.

`:wq` will write your buffer to disk and **update modification timestamp**.

`:x` will only write when there is any changes on your buffer. If your buffer remain the same, then the **modification timestamp will be untouched.**