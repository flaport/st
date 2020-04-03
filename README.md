# st - simple terminal
st is a simple terminal emulator for X which sucks less.

## Repository branches
Each branch of this repository (apart from
[master](https://github.com/flaport/st/tree/master) and
[upstream](https://github.com/flaport/st/tree/upstream)) is
responsible for a single patch to vanilla st.  Each patch was first
applied on the upstream. Then any additional changes, optimizations
and preferences related to the patch were also applied inside the
branch *before* the branches were merged into master. This way
personal adaptations and improvements to each standard patch are kept
seperately allowing *you* to select which adapted patches to apply to
your build of st.

A list of all patches merged into master in the order they were applied:
* [alpha](https://github.com/flaport/st/tree/alpha) ‧ standard alpha patch + xresources integration + escape sequences for alpha updates of already open windows + keep alpha during pywal updates 💪 ‧ [download customized patch](https://github.com/flaport/st/compare/3848301..alpha.diff)
* [xresources](https://github.com/flaport/st/tree/xresources) ‧ standard xresources patch + escape sequences for color updates of already open windows (perfect for pywal) 👍 ‧ [download customized patch](https://github.com/flaport/st/compare/3848301..xresources.diff)
* [scrollback](https://github.com/flaport/st/tree/scrollback) ‧ *all* the scrollback patches ⬆ ‧ [download combined patch](https://github.com/flaport/st/compare/3848301...scrollback.diff)
* [newterm](https://github.com/flaport/st/tree/newterm) ‧ standard newterm patch 📺 ‧ [download customized patch](https://github.com/flaport/st/compare/3848301...newterm.diff)
* [copyurl](https://github.com/flaport/st/tree/copyurl) ‧ standard copyurl + custom multi-line url copy added 🤗 ‧ [download customized patch](https://github.com/flaport/st/compare/3848301...copyurl.diff)
* [openclipboard](https://github.com/flaport/st/tree/openclipboard) ‧ standard openclipboard patch 📋 ‧ [download customized patch](https://github.com/flaport/st/compare/3848301...openclipboard.diff)
* [font2](https://github.com/flaport/st/tree/font2) ‧ standard font2 patch + color emojis *if* [libxft-bgra](https://gitlab.freedesktop.org/xorg/lib/libxft/-/merge_requests/1) is installed *else* non-color emoji with normal libxft. No crashing. 🙌 ‧ [download customized patch](https://github.com/flaport/st/compare/3848301...font2.diff)


Extra:
* [download xresources + alpha together](https://github.com/flaport/st/compare/f6ad6ef..703e78f.diff)

## Requirements
* In order to build st you need the Xlib header files.
* In order to have color-emojis in the terminal, you'll want
[libxft-bgra](https://gitlab.freedesktop.org/xorg/lib/libxft/-/merge_requests/1)
to be installed.


## Installation
Edit config.mk to match your local setup (st is installed into
the /usr/local namespace by default).

Afterwards enter the following command to build and install st (if
necessary as root):

```
    make clean install
```


## Running st
If you did not install st with make clean install, you must compile
the st terminfo entry with the following command:

```
    tic -sx st.info
```

See the man page for additional details.

## Credits
* The program `st` was based on Aurélien APTEL `bt` source code.
* This fork is based on `st` [https://st.suckless.org/](https://st.suckless.org/)

