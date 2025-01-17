keynav
================

Control the mouse with the keyboard.

Original project: http://www.semicomplete.com/projects/keynav

Trevor's (@Trevcan) fork of keynav.

# TODO
- add basic modes (just like `vim`)
- add way to scroll (e.g. press `s` to enter into scroll mode) j,k to scroll up and down. h,l to scroll sideways.\
Use capital letters to increase multiplier of scroll numbers.\
Add no need to 'click' or forcibly focus window, just scroll to the window which has the cross and then - if the
user was on another window - select the previous window.
- add way to select grids (maybe `g` ?) (just like in one of the examples) but select them with j,k,h,l and then press enter


also...
   make a ZoomIt port to linux (X server)

   https://docs.microsoft.com/en-us/sysinternals/downloads/zoomit


Compiling
---------

You may need some extra libraries to compile keynav.  On Debian and Ubuntu you can install these packages:

    sudo apt-get install libcairo2-dev libxinerama-dev libxdo-dev

Next you simply run make:

    make

This will produce an executable `./keynav` which may be run directly (or copied
somewhere in your path). You can also install (by default directly to `/usr`)
via `make install`.

On FreeBSD (and, I expect, other non-GNU platforms), you will want to use gmake.


FAQ
---

Q: What platforms are supported?
A: keynav should work on nearly any Unix-like that runs X11. It has been
confirmed to work on extremely varied GNU/Linux systems (incuding RPM-based,
Debian derivatives, musl-based systems, and Arch), and FreeBSD. If you get it to
run elsewhere, please let me know so I can add it to the list. If you try to run
it on another Unix-like and have trouble, please get in touch and I'll try to
help. If attempting to run elsewhere, note that we currently have a dependency
on GNU Make (gmake), and it hasn't been tested with many compilers yet.

Q: Does it work on Android/Windows/Wayland/iOS/...?
A: Sadly, no; keynav is totally dependent on X11, and porting it to any other
graphical system would really be a clone/rewrite. Although I am aware of no
exact analogues on other systems, I suggest looking into Tasker (Android),
AutoHotKey (Windows), and AppleScript (macOS). If you find something that works,
let me know and I'll consider adding it to this list.

Q: Can I use keynav to scroll?
A: Yes! X11 represents mouse scrolling as key presses, so you just add the
relevant stanza to your keynavrc.  Mouse buttons are
1=left, 2=middle, 3=right, 4=scroll-up, 5=scroll-down, 6=scroll-left, 7=scroll-right. So for example to scroll up with i and down with e:
```
i click 4,end
e click 5,end
```
or to keep scrolling without having to re-invoke keynav, remove the end command from the bindings, like this:
```
i click 4
```

debian info:

packages needed to build:
libxinerama-dev
libglib2.0-dev
libcairo2-dev
libxdo-dev

## Tree

keynav
├── CHANGELIST
├── examples
│   ├── keynavrc
│   └── keynavrc.jordan
├── keynav.c
├── keynav.pod
├── LICENSE
├── Makefile
├── README.md
├── test.sh
├── TODO
└── version.sh

1 directory, 11 files
