---
title: Screen orientation in Sway
draft: false
next: docs/tmux
---

Presently, I run [endeavouros](https://endeavouros.com) with [sway](https://swaywm.org) on my beast. I used xrandr in the past, and discovered arandr for xserver based desktop environments. I discovered swaymsg "outputs" recently.

Get all the display outputs, along with their positions, modes and rotation
```
swaymsg -t get_outputs
```

Following is to setup a mode and DP-2 is name of the display, retrieved from above.
```
swaymsg output DP-2 mode 1920x1080@60hz
```

Can be rotated as follows.
```
swaymsg output DP-2 transform 90 
```

Extra bit to have positions set.
```
swaymsg output DP-2 position 3840,0 
```

Finally compose all that together and add it sway config
```
output DP-2 mode 1920x1080@60hz position 3840,0 transform 90 
```
