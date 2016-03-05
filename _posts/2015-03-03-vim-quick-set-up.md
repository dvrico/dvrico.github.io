---
layout: post
title: Vim+Tmux - Thoughts and Advice for New Users
description: Interested in vim, but don't know where to start? Look no further!'
comments: true
categories: programming
---

I decided to try the Vim+Tmux combo out for a month. It has definitely been a very
rocky journey, full of bumps and bruises, but I feel confident going into week three now.
I wanted to share some (newbie) insight and give some advice for those who are interested in
trying Vim/Tmux out, so that others can avoid some of the very unecessary pains in the beginning
of the journey.

Stick to the basics!
====================
Vim has a high learning curve. Joined together with tmux and that's a black eye waiting to
happen if your not careful. But do you know what guarantees two black eyes? 
Lots and lots of plugins. 

I downloaded and installed a bunch of plugins for vim and tmux when I first started because
the internet said I absolutely needed them. Soon after I found myself drowning in a sea
of (awesome) command shortcuts. It was just too much. I was trying to learn the basic
vim commands, tmux commands, and the plugin commands all at once. I soon became very frustrated.

I found out that becase I hadn't used vim extensively, I couldn't justify the usefulness
of all these plugins. They were complicating things for me because **I didn't know the downside
of vanilla vim.** That said, get to know vim with very few plugins first. This allows you to discover
the downsides yourself. From there, feel free to use plugins to make up for the downsides
you have discovered. Experience first, fix later.

Here are some plugins I had installed in the beginning of my adventure:

*    [Javascript syntax highlighting](https://github.com/jelera/vim-javascript-syntax)
*    [Python syntax highlighting](https://github.com/hdima/python-syntax)
*    [Gruvbox color scheme](https://github.com/morhetz/gruvbox) (I can't resist a good theme)

Learn Movement Commands Really Well
===================================
Nothing is more frustrating than taking twenty seconds longer to get half way down the page
to a specific line then to a specific word while only using vim's h, j, k, l arrow keys.

Because I didn't take the time to really learn the movement commands, I found myself cheating; using arrow keys,
the mouse, and, at one point, a different editor! I took a step back, downloaded a [nifty cheat
sheet](https://bitbucket.org/tednaleid/vim-shortcut-wallpaper/raw/tip/vim-shortcuts.png) (thanks to [Ted Naleid](http://naleid.com/blog/2010/10/04/vim-movement-shortcuts-wallpaper/a)) and forced myself only move the cursor via
move commands. Sure it took longer at first, and I looked pretty dumb
shouting commands out loud to help me remember faster (it works, try it!), but
it helped in the long run. I can now resonably get around the vim, and each day
I find myself getting faster. It feels great when you start noticing vim fading into the background environment 
to help rather than impede.

 I made this [cheat sheet](http://www.viemu.com/vi-vim-cheat-sheet.gif) my desktop background shortly after. 

Don't Forget About Tmux
=======================
Honestly, tmux is so much easier to learn after dealing with vim. Just make sure you know the basic commands well (or
keep a list handy) and you'll be good to go. One thing I changed right off the bat was the default tmux key (ctrl-b) to
ctrl-a. The inspiration came from Daniel over [unwiredcouch.com](https://www.unwiredcouch.com/). In fact when you want
 to take your tmux config to the next level I suggest you read his
 [post](https://www.unwiredcouch.com/2013/11/15/my-tmux-setup.html) about it.

And of course I couldn't resist a good tmux [theme](https://github.com/edkolev/tmuxline.vim) either.

Conclusion
==========
I'm happy with my results so far, and I'm glad I forced myself to stick with for a month. I recommend that you try
vim+tmux for a month before making any rash decisions. The first week will be rough, I can guarantee it. However, 
if you keep at it (code every day!) you'll soon become a vim+tmux pro. Hopefully this article can help jumpstart
that.
