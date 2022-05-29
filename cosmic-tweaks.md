# COSMIC tweaks (in late May 2022)

Here are some tweaks to make COSMIC better who doesn't need hand holding with respect to Linux and other practical preferences.

## 1: Disable Pop Shop auto alerts

Correct [question](https://old.reddit.com/r/pop_os/comments/rj6k8u/remove_app_suggestions_in_launcher/), but the answer is elsewhere.

The referenced [post](https://old.reddit.com/r/pop_os/comments/rdz3as/how_to_completely_disable_pop_shop/ho4u4bq/) has the answer.

Run these commands in a terminal emulator instance:
```
$ mkdir -p ~/.config/autostart
$ cp /etc/xdg/autostart/io.elementary.appcenter-daemon.desktop ~/.config/autostart/
$ echo "X-GNOME-Autostart-enabled=false" >> ~/.config/autostart/io.elementary.appcenter-daemon.desktop
```

Restart your machine to have the changes take effect.

This will disable for system components and individual packages (such as Firefox), but will still let you know if there's a system upgrade, such as an upgrade from Pop!\_OS 21.10 to Pop!\_OS 22.04 LTS.

### A note: totally disabling Pop Shop in the background

If you really wanted totally disabling Pop Shop in the background, then run:
```
systemctl disable pop-upgrade.service
```

[Source](https://old.reddit.com/r/pop_os/comments/o5s9cx/disable_updates_check_by_popshop_on_startup/)

## 2: Change keyboard shortcuts for switching between application windows

Run these commands in this exact order in a terminal emulator instance:
```
$ gsettings set org.gnome.desktop.wm.keybindings switch-applications "[]"
$ gsettings set org.gnome.desktop.wm.keybindings switch-applications-backward "[]"
$ gsettings set org.gnome.desktop.wm.keybindings switch-windows "['<Alt>Tab', '<Super>Tab']"
$ gsettings set org.gnome.desktop.wm.keybindings switch-windows-backward  "['<Alt><Shift>Tab', '<Super><Shift>Tab']"
```

[Source](https://unix.stackexchange.com/questions/619789/how-do-i-cycle-through-windows-with-alttab-on-pop-os)

## 3: Disable all animations

In a terminal emulator instance, run:
```
$ gsetting set org.gnome.desktop.interface enable-animations false
```

This makes GNOME run a little faster by reducing visual stuttering.

This can be done in all distros with GNOME.

## 4: Get rid of screen tearing

Execute the following in a terminal:
```
$ sudo vim /etc/X11/xorg.conf.d/20-intel.conf
```
and edit the file so that this section looks like this:
```
Section "Device"
    Identifier "Intel Graphics"
    Driver "intel"
    Option "TearFree" "true"
EndSection
```

[Source](https://togaware.com/linux/survivor/Screen_Tearing_on_X11.html)

To be clear, this also happens in default Ubuntu with GNOME and applies to hardware with integrated graphics (and no hybrid/discrete GPU).

I think screen tearing still happens, but it's much less on the SP1.

## 5: All other changes in the GUI settings from System76's defaults

Here are the changes I made in the GUI Settings application:

* Wi-Fi: turn off, since I use Ethernet.
* Bluetooth: turn off always, since I have no use for Bluetooth on desktop.
* Desktop
    * Super Key Action: view Workspaces, instead of the default Launcher.
    * Top Bar
        * Window Controls: Turn on "Show Maximize Button"
    * Background: change to something dark
    * Appearance: choose the Dark theme (always)
    * Dock
        * Dock Options
            * Turn off "Extend dock to the edges of the screen"
            * Turn off "Show Launcher Icon in Dock"
            * For "Icon Click Action", select: "Launch or Minimize Windows"
        * Dock Visibility
            * Intelligently Hide
            * For "Show Dock on Display", select: "Primary Display"
    * Workspaces
        * For "Placement of the Workspace Picker", pick: "Along the right side"
* Privacy > Location Services: Turn off (but this is off by default in Pop!\_OS upon first boot after installation)
* Sharing: Turn off (I don't need either Remote Desktop or Media Sharing)
* Sound
    * Mute all Speakers (both built-in and SP2 docking, common sense AV etiquette/procedure)
    * Mute all Microphones (for same reason)
    * Don't accidentally shift the audio Balance!
* Battery > Suspend & Power Button: Turn on "Show Battery Percentage"
* Displays
    * Displays
        * Built-in display
            * Scale: 100%
            * Refresh Rate: 59.97 Hz (apparently this is just 60 Hz)
            * Absolutely no fractional scaling
        * HiDPI Daemon
            * For "Enabled", turn it off!
                * This causes endless problems on Pop!\_OS 22.04 upon login.
            * For "Mode", keep on
                This toggle turns back on upon login, no matter what.
    * Night Light: turn on
        * For Schedule: "Sunrise to Sunset"
            * Let the OS decide when these times are, especially if you don't use a VPN outside of your current timezone
        * Color Temperature: place scale picker 2/3 and the right end, w.r.t the left end.
* Printers
    * Hopefully all printers you plug in directly via USB work "out of the box", since Pop!\_OS preinstalls the most well known printer drivers for popular printer brands.
* Accessibility
    * Turn on "Always Show Accessibility Menu"
    * Seeing
        * Turn on "Large Text"
* Date & Time
    * Time Format: Pick "AM/PM", if this wasn't already done by default in the Pop!\_OS installer
* OS Upgrade & Recovery
    * OS Upgrade mostly unnecessary if you use regularly `$ sudo apt update && sudo apt upgrade` in the CLI.
        * I should figure out how to update the Recovery partition via the CLI...
    * System and Application Updates
        * Turn off "Automatic Updates"
        * For "Show Update Notifications", pick: "Weekly"

### Some other items to take care of

* Startup Applications: uncheck "Flatpak transition"
    * We don't deal with Flatpaks here...
* Disable Flatpak in Pop!\_Shop: Gear/Cog icon > Flatpak tab > Delete the single Flatpak source
    * Flatpaks, begone!

[//]: # (8:41am on May 26, 2022)
