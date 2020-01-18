---
title: Prevent HDMI from losing signal after lock/blank screen
date: 2018-05-17T10:44:20.317Z
tags: ["til"]
---
```
This worked for me:

xset -dpms
The -dpms option disables DPMS (Energy Star) features.

For permanent solution:

echo "xset -dpms" >> ~/.xinitrc
If it doesn't work or want more user friendly way, add xset -dpms to:

System Tools → Preferences → Startup Applications
```

(Thanks goes to [Ingo Karkat] and [user.dz])


Reference: 
- man xset
- https://askubuntu.com/questions/696738/prevent-monitor-from-losing-signal-after-screen-saver-lock-activates


[Ingo Karkat]: https://askubuntu.com/users/72217/ingo-karkat
[user.dz]: https://askubuntu.com/users/26246/user-dz
