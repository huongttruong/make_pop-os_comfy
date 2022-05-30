# Explanation for DVD menu playing in VLC

```
$ sudo apt install libdvdcss2  # Install the package
$ sudo dpkg-reconfigure libdvd-pkg  # Then build the package, due to a legal technicality with DMCA
```

I think this only matters on Debian-/Ubuntu-based distros.

On Arch Linux-based distros (like Manjaro), the packages for playing optical
disc drive (CD, DVD, and Blu-ray) seem to be automatically installed with mpv
and/or VLC.

