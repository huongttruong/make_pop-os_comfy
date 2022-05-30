# Verbose package versions for APT upgrades

To list each package on its own line and the change of version numbers, create a file using:
```
$ sudo /usr/apt/apt.conf
```
and put the following line in the file:
```
APT::Get::Show-Versions "true";
```

[Source](https://askubuntu.com/questions/928785/how-can-i-enable-verbose-versions-for-apt-get-and-apt-by-default), which can be quite hard to find without searching `"apt.conf verbose"` and looking at least 5 results deep in DuckDuckGo or Startpage.

