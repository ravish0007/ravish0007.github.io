---
title: Loophole in a Loophole
type: blog
---

When I surf on the web, sometimes there won’t be a limit to curiosity. When I look at a catchy program, I want to try it at that very instant, but this is almost impossible in a typical work computer. For each software, I either had to look into the employer’s custom app store or write a mail to local IT and wait for several hours or sometimes days, and it better had a business use case to them.

There were restrictions on so many domains, web extensions were out of reach, annoying Windows GUI. All in all, it was terrible!

I'm fully aware of this issue not being personal, but having accurate security concern, but I wanted an escape very badly, it started with my frequent visits to Google’s <a href="https://cloud.google.com/shell/docs"> cloud shell</a>. I had no idea about the “web-preview” feature of it. Somehow, I came with an idea of having a browser inside a browser. I knew about a CLI web browser called <a href="https://www.brow.sh/">browsh</a>, and it had a server mode, which I tried on cloud shell and there it was, a browser inside a browser. It wasn’t appealing as it was pixelated.

I went on searching for a project, which takes care of my “browser in a browser” requirement. I tried to frame a question as precisely as possible but had to unstick <a href="https://xyproblem.info/">XY</a> off of my face in ArchLinux discord, but someone understood it’s about finding a loophole in a loophole and hence the title and finally stumbled on ViewFinder. It took me a while to get it running and there was pure relief on port 8002.

It used to crash because many threads were getting created while loading heavy pages. I kept on going, but this time I wanted a VNC in a browser. Luckily this wasn’t hard as the previous hunt and came across novnc for the very first time. Fascinating! I got it working after putting a whole afternoon into it and some more time on making a <a href="https://gist.github.com/ravish0007/c9884cdd90e8cc2ffaacacd658cc05d8">script</a> to work.

Anyway, now I have a full-fledged Linux environment in a browser tab, which is also crazy fast. There were no restrictions whatsoever inside that machine, I could visit any site I wanted, try beautiful programs and carry out weird experiments. Voilà! Freedom and joy in the end. Well! The sound wouldn’t work, I had my ways around it.

What followed after many months is a single command in termux will set up the environment whenever I needed it. That is all for now, find it <a href="https://github.com/ravish0007/termux-gcloud">here</a> to hack around.
