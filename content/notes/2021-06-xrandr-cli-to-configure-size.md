---
title: "xrandr: cli to configure size"
date: 2021-06-18T06:11:15.022Z
tags:
  - til
---
definition from it's manual:

> xrandr - primitive command line interface to RandR extension
>
> Xrandr is used to set the size, orientation and/or reflection of the outputs for a screen. It can also set the screen size.

To rotate screen orientation back to normal

> xrandr -o normal

To show list output with supported resolution

> xrandr

To disable one output

> xrandr --output ID --off

To set resolution of HDMI-1 output to 3440x1440

> xrandr --output HDMI-1 --mode 3440x1440