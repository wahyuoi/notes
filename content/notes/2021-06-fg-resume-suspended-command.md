---
title: "fg: resume suspended command"
date: 2021-06-18T09:47:29.195Z
tags:
  - til
---
I just suspended a vim process by accidentally hit Ctrl+Z (yeah I know, it was not accident at all). 

The terminal will provide the PID for that process, like this one 

![](/images/image-6-.png)



To resume the process, I need to invoke `fg` with the process name, 

> fg %vim
