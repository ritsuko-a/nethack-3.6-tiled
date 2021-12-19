# nethack tiled font for xterm

Long time ago, [Roar André Lauritzsen](http://www.pvv.org/~roarl/nethack/nethack.html)
made «pseudotiled» font for NetHack 3.4

I've just adapted this font to mainline nethack 3.6.x and curses interface.

## How to use
* Install patched [nethack16.bdf](fonts-patched/nethack16.bdf) and
[nethack16B.bdf](fonts-patched/nethack16B.bdf) somewhere in your X11 font path.

* Add [symbols](symbols) to nethack symbols (usually in
`/usr/lib/games/nethack/symbols`)

* Enable symset in config:
```
OPTIONS=symset:Fontgraphics
OPTIONS=color,lit_corridor,windowtype:curses,eight_bit_tty
```

* Start XTerm with new font
```sh
#!/bin/sh
exec xterm                                                                    \
      -fg   white                                                             \
      -bg   black                                                             \
      -cr   red                                                               \
      +sb                                                                     \
      -bdc                                                                    \
      -en   "ISO 8859-1"                                                      \
      -font -misc-nethack-medium-r-normal--24-160-100-100-c-160--custom       \
      -xrm  "xterm*color0:#000000"                                            \
      -xrm  "xterm*color1:#d00000"                                            \
      -xrm  "xterm*color2:#00b000"                                            \
      -xrm  "xterm*color3:#c07000"                                            \
      -xrm  "xterm*color4:#3030ff"                                            \
      -xrm  "xterm*color5:#c800c8"                                            \
      -xrm  "xterm*color6:#00c8c8"                                            \
      -xrm  "xterm*color7:#d0d0d0"                                            \
      -xrm  "xterm*color9:#ffb000"                                            \
      -xrm  "xterm*color10:#40ff00"                                           \
      -xrm  "xterm*color11:#ffff40"                                           \
      -xrm  "xterm*color12:#0090ff"                                           \
      -xrm  "xterm*color13:#ff00ff"                                           \
      -xrm  "xterm*color14:#70ffff"                                           \
      -xrm  "xterm*color15:#ffffff"                                           \
      -xrm  "xterm*renderFont: false"                                         \
      -geometry   140x60                                                      \
      -e nethack

```

Symset is fully compatible with original fonts as well, but only with tty interface.
