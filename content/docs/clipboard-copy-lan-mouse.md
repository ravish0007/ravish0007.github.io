---
title: Copy clipboard in wayland
type: docs
prev: living-clojure
next: docs/clipboard-copy-lan-mouse
---

"lan-mouse" is mouse and keyboard sharing program comes with swayWM support but with a caveat of not sharing clipboard, below is hack found on their github issue to share clipboard

dependency: wl-clipboard

```
#!/bin/bash
SEND="user@remotehost"
notify-send -i clipboard "Copying clipboard to '$SEND'..."
if wl-paste --no-newline | ssh "$SEND" "env WAYLAND_DISPLAY='wayland-1' wl-copy > /dev/null 2>&1"; then
    notify-send -i edit-copy "Clipboard copied to '$SEND'"
else
    notify-send -i error "Failed to copy clipboard to '$SEND'"
fi
```
