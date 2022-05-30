# Disable touch screen

```
$ sudo vim /usr/share/X11/xorg.conf.d/40-libinput.conf
```

Add this line to the `touchscreen` section:
```
Option "Ignore" "on"
```

[Source](https://www.youtube.com/watch?v=7qZBiOsXI_s), which has now been
unlisted.  I'll try to find another [semantic](https://en.wikipedia.org/wiki/Semantic_Web) version,
if I can.

