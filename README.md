# st - simple terminal
st is a simple terminal emulator for X which sucks less.

## Patches
Multiple patches were applied. Each applied patch can be found in a separate
branch of this repository. Each patch was first applied on the upstream (commit
[3848301](https://github.com/flaport/st/tree/upstream)). Then any additional
changes, optimizations and preferences related to the patch were also applied inside the 
branch *before* the branch was merged into master. This way adaptations to each patch
are kept seperately allowing *you* to select which adapted patches to apply to
your build of st.

A list of all patches merged into master (in the order they were applied):
* alpha
* xresources
* scrollback
* newterm
* copyurl
* openclipboard

## Requirements
In order to build st you need the Xlib header files.


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

