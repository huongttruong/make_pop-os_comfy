# Symantec VIP Access

Make sure that `python3-pip` is installed before proceeding.

First, install `python-vipaccess` from [pip](https://en.wikipedia.org/wiki/Pip_(package_manager)), the established package manager for Python:
```
$ pip install python-vipaccess --user
```

If you examined the standard output, then you may have noticed the following
warning which goes something like:
```
The script python-vipaccess is installed in '/home/user/.local/bin' which is not on PATH.
Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.
```

(I didn't copy and paste the standard output message before restarting the
computer.)

(Thanks for something similar, [Stack Exchange](https://stackoverflow.com/questions/62822956/how-to-make-pip-install-to-path-on-linux).)

However, you don't have to worry about this due to something later down the
procedure.

Next, copy and paste `.vipaccess` from Keybase's KBFS into the home directory so it is
at `~/.vipaccess`.

Then, understand why the warning about the $PATH [environmental variable](https://wiki.archlinux.org/title/Environment_variables#Globally)
isn't a concern.  If you check the Bash [configuration file](https://wiki.archlinux.org/title/Bash#Configuration_files)
`~/.profile` in Pop!\_OS, then you will see the following file tail:
```
# set PATH so it includes user's private bin if it exists
if [ -d "$HOME/.local/bin" ] ; then
    PATH="$HOME/.local/bin:$PATH"
fi
```

Because this is a (terse way of writing a Bash) conditional statement, this part
of `.profile` won't activate until the specified file path is created.

Lastly, simply restart the machine and log back in to see that now `vipaccess`
is an executable that can be used with the default "tab-tab" autosuggestion in
any terminal emulator instance.

## Unnecessary Commentary

I have to put this in the cloud, or else I'm liable to mess up and wipe my
computer by accident again.

The [Symantec VIP](https://m.vip.symantec.com/) 2FA app is unfortunately
proprietary.

I think there's little to no reason why [TOTP](https://en.wikipedia.org/wiki/Time-based_one-time_password)
apps for [2FA](https://en.wikipedia.org/wiki/Multi-factor_authentication) exist.

This is because everything would work with [Google Authenticator](https://en.wikipedia.org/wiki/Google_Authenticator)
and any other open-source Google Authenticator-compatible reimplementation, such
as [Aegis](https://getaegis.app/).

Even non-technical Henry from Techlore [understands](https://www.youtube.com/watch?v=iXSyxm9jmmo)
that proprietary TOTP apps like Symantec VIP and Authy are fundamentally scams
on a conceptual level.

In fact, the currently maintained fork of [`python-vipaccess`](https://github.com/dlenski/python-vipaccess)
shows that companies are essentially wrapping an open-source software core with
proprietary branding on the outside like wrapping paper on the software level.

[//]: # (4:07pm on May 29, 2022)
