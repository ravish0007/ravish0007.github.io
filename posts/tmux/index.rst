.. title: Tmux is "Ahh! Nice!"
.. slug: tmux
.. date: 2021-10-18 17:57:10 UTC+05:30
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text

I encountered `tmux <https://github.com/tmux/tmux>`_ when I was looking for a method to run stuff in background (mitigating ssh session termination). I later found out that it can do terminal multiplexing which is super impressive. It was quite some time ago.

I was only able to do,
 - Create horizontal and vertical panes
 - Move between panes using prefix-o 
 - Create sessions and attach/detach them (confusing numbers)

It was quite painful, felt not so flexible and was very ignorant to refine them.
Shout out to `Jay <https://www.jaylacroix.com>`_ for making an awesome `series <https://www.learnlinux.tv/getting-started-with-tmux/>`_ on tmux. 

It was 2 A.M already but kept on watching it, and I was able to pick up,
 - Prefix-z to zoom in and out of current pane
 - Prefix-c to create windows, (prefix-,) to rename them and prefix-[n|m] to move between them.
 - Creating sessions with better names made a lot of difference

In the end of his series, he dropped his `config <https://pastebin.com/CDEVZTSC>`_ and I fiddled around with it and made `mine <https://github.com/ravish0007/dotfiles/blob/main/tmux.conf>`_ which fits my taste.

Well, what is so special about it ?, you may ask !
:raw-html:`<br \>`
Umm...! Nothing really ! It just feels home :)

