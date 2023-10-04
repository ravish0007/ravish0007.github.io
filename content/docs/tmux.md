---
title: "Ahoy Tmux! Here we meet again!"
date: 2021-10-18T17:57:11+05:30
draft: false
next: docs/living-clojure
---

I encountered [tmux](https://github.com/tmux/tmux) when I was looking for a method to run stuff in the background (mitigating ssh session termination). 
I later found out that it can do terminal multiplexing which is super impressive. It was quite some time ago.

Previously, I was only able to,
   -  Create horizontal and vertical panes
   -  Move between panes using prefix-o
   -  Create sessions and attach/detach them (confusing numbers)

It was quite painful, felt not so flexible and was very ignorant to refine them. 
Shout out to [Jay](https://www.jaylacroix.com) for making an awesome [series](https://www.learnlinux.tv/getting-started-with-tmux/) on tmux.

It was 2 A.M already but kept on watching it, and I was able to pick up,
   -  Prefix-z to zoom in and out of the current pane
   -  Prefix-c to create windows, (prefix-,) to rename them and prefix-\[n\|m\] to move between them
   -  Creating sessions with better names and switching (prefix-s) between them made a lot of difference

At the end of his series, he dropped his [config](https://pastebin.com/CDEVZTSC) and I fiddled around with it and made [mine](https://github.com/ravish0007/dotfiles/blob/main/tmux.conf) that fits my taste.

Well, what is so special about it? you may ask!
Umm! Nothing really! It just feels home.
