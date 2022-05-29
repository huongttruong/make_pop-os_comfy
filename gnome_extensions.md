# GNOME Extensions

I just download the [add-on](https://addons.mozilla.org/en-US/firefox/addon/gnome-shell-integration/) for Firefox (since LibreWolf is my main browser and I only have Firefox as a backup browser).

I've never had any luck with the `chrome-gnome-shell` package for Debian, as described by the [GNOME Wiki](https://wiki.gnome.org/Projects/GnomeShellIntegrationForChrome/Installation).

## Desired 3rd-party Extensions

* [Clipboard History](https://extensions.gnome.org/extension/4839/clipboard-history/)
* [OpenWeather](https://extensions.gnome.org/extension/750/openweather/)
* [Lock Keys](https://extensions.gnome.org/extension/36/lock-keys/)
* [Caffeine](https://extensions.gnome.org/extension/517/caffeine/)
* [Desaturate All](https://extensions.gnome.org/extension/1102/desaturate-all/)
    * Requires modifications (see below)

Find these at `~/.local/share/gnome-shell/extensions`

### Install these 3rd-party Extensions after removing them system-wide

(This is to deny these desired extensions from being installed system-wide -- hopefully.)

* [Places Status Indicator](https://extensions.gnome.org/extension/8/places-status-indicator/)
* [Removable Drive Menu](https://extensions.gnome.org/extension/7/removable-drive-menu/)
* [Screenshot Window Sizer](https://extensions.gnome.org/extension/881/screenshot-window-sizer/)
* [Workspace Indicator](https://extensions.gnome.org/extension/21/workspace-indicator/)

This is the command to remove these system-wide while working in `/usr/share/gnome-shell/extensions`:
```
$ sudo rm -rfv drive-menu@gnome-shell-extensions.gcampax.github.com places-menu@gnome-shell-extensions.gcampax.github.com screenshot-window-sizer@gnome-shell-extensions.gcampax.github.com
```

### Only leave DING NG (for desktop icons)

This is fine, since there's an APT package for this.

### Fix for Desaturate All

From [this](https://wiki.archlinux.org/title/GNOME/Troubleshooting#Extensions_do_not_work_after_GNOME_3_update), use:
```
gsettings set org.gnome.shell disable-extension-version-validation true
```

Next, download Desaturate All with the browser of the locally installed GNOME Shell integration browser add-on.

Then, run:
```
gsettings set org.gnome.shell disable-extension-version-validation false
```

Afterwards, navigate to `~/.local/share/gnome-shell/extensions/desaturate_all@nicolas.brack.mail.be`.

Edit this section of `extension.js`; change this section:
```
                          x_fill: true,
                          y_fill: false,
                          track_hover: true });
```
to this:
```
                          track_hover: true });
    button.x_fill = true;
    button.y_fill = false;
```

Lastly, as described on the [ArchWiki](https://wiki.archlinux.org/title/GNOME/Troubleshooting#When_an_extension_breaks_the_shell), change `metadata.json` so that the `"shell-version"` reads as:
```
  "shell-version": [
    "3.18.5",
    "42"
  ],
```

Log out of GNOME and sign back in to see the changes.

## OpenWeather

Don't need to install `gnome-icon-theme` anymore.

## Remove system Extensions

At `/usr/share/gnome-shell/extensions`, remove the following directories:
```
apps-menu@gnome-shell-extensions.gcampax.github.com
auto-move-windows@gnome-shell-extensions.gcampax.github.com
launch-new-instance@gnome-shell-extensions.gcampax.github.com
native-window-placement@gnome-shell-extensions.gcampax.github.com
user-theme@gnome-shell-extensions.gcampax.github.com
window-list@gnome-shell-extensions.gcampax.github.com
windowsNavigator@gnome-shell-extensions.gcampax.github.com
```
When in the directory, remove them with:
```
$ sudo apt rm -rfv apps-menu@gnome-shell-extensions.gcampax.github.com auto-move-windows@gnome-shell-extensions.gcampax.github.com launch-new-instance@gnome-shell-extensions.gcampax.github.com native-window-placement@gnome-shell-extensions.gcampax.github.com user-theme@gnome-shell-extensions.gcampax.github.com window-list@gnome-shell-extensions.gcampax.github.com windowsNavigator@gnome-shell-extensions.gcampax.github.com
```

Next, restart and then log back in.

To create a "stub", install all of the removed extensions as a per user extension, then remove them.  Hopefully this will stop the Pop!\_OS system from installing these GNOME Extensions back.

Here are the links:

* [Applications Menu](https://extensions.gnome.org/extension/6/applications-menu/)
* [Auto Move Windows](https://extensions.gnome.org/extension/16/auto-move-windows/)
* [Launch new instance](https://extensions.gnome.org/extension/600/launch-new-instance/)
* [Native Window Placement](https://extensions.gnome.org/extension/18/native-window-placement/)
* [User Themes](https://extensions.gnome.org/extension/19/user-themes/)
* [Window List](https://extensions.gnome.org/extension/602/window-list/)
* [windowNavigator](https://extensions.gnome.org/extension/10/windownavigator/)

[//]: # (1:02am on May 25, 2022)
[//]: # (11:35am on May 28, 2022)
