# st - simple terminal
st is a simple terminal emulator for X which sucks less.

## Patches
Each patch applied to this version of st lives in a separate branch in
this repository. Such a branch can either be a vanilla patch like they
can be downloaded from the suckless website, or a modified patch, or a
completely custom patch. Below you find all the applied patches in the
order they were merged into the master branch of this repository.

#### alpha + xresources

* download [my combined patch](https://github.com/flaport/st/compare/upstream..alpha+xresources.diff) ‧ [my alpha patch](https://github.com/flaport/st/compare/upstream..alpha.diff) ‧ [my xresources patch](https://github.com/flaport/st/compare/upstream..xresources.diff)
* see [combined branch](https://github.com/flaport/st/tree/alpha+xresources) ‧ [alpha branch](https://github.com/flaport/st/tree/alpha) ‧ [xresources branch](https://github.com/flaport/st/tree/xresources)

Combining `alpha` with `xresources` only makes sense, because they are
often defined in the same Xresources file. Moreover, I patched the
URXVT escape sequences into it as well. This will make st listen to
pywal updates 💪.

#### newterm

* download [ patch](https://github.com/flaport/st/compare/upstream..newterm.diff)
* see [branch](https://github.com/flaport/st/tree/newterm)

Spawn a new terminal in the same folder with `alt+enter` 📺.

#### copyurl

* download [my customized patch](https://github.com/flaport/st/compare/upstream...copyurl.diff)
* see [branch](https://github.com/flaport/st/tree/copyurl)

Jump between urls visible in terminal with `alt+n` (forward) or
`alt+m` (backward) and copy the url to the clipboard. This patch is
perfect in conjunction with the `openclipboard` patch. I modified the
standard copyurl patch to work with multi-line urls 🌐.

#### openclipboard

* download [my customized patch](https://github.com/flaport/st/compare/upstream...openclipboard.diff)
* see [branch](https://github.com/flaport/st/tree/openclipboard)

The keybinding `alt+g` opens whatever is on the clipboard with
`xdg-open`📋.

#### font2

* download [my customized patch](https://github.com/flaport/st/compare/upstream...font2.diff)
* see [branch](https://github.com/flaport/st/tree/font2)

St does not listen to the fallback fonts defined in your fontconfig:
st will only use the first match. Hence to have proper fallback fonts
defined, one needs to define those with the `font2` patch.


#### ligatures

* download [my customized patch](https://github.com/flaport/st/compare/upstream...ligatures.diff)
* see [branch](https://github.com/flaport/st/tree/ligatures)

Enable font-ligatures. Note that a ligature-capable font needs to be
defined as your *primary* st font for this to work.

#### scrollback

* see my [scroll repository](https://github.com/flaport/scroll)

Scrollback is **not** implemented with the scrollback patch. In stead,
a separate tiny (suckless) program, `sroll`, is used which implements
this feature.  According to the suckless developers, this solution is
much better than implementing the scrollback in st itself because
having a different program allows to use it in any other program
without doing modifications to those programs.

## Other branches

#### v2
This version. Should be more or less up to date with master.

#### v1
A very similar build as v2 or master but with all the scrollback
patches applied as well.

#### scrollback

* download [combined patch](https://github.com/flaport/st/compare/upstream...scrollback.diff)
* see [combined branch](https://github.com/flaport/st/tree/scrollback)

All the scrollback patches together. I do not apply this patch anymore
since st now supports external scrollback programs.

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

