# Disable touch screen

```
$ sudo vim /usr/share/X11/xorg.conf.d/40-libinput.conf
```

Add this line to the `touchscreen` section:
```
Option "Ignore" "on"
```

[//]: # (6:57pm on May 23, 2022)
