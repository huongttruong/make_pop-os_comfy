# Make Pop!\_OS Comfy

The following files here document what I need to change for Pop!\_OS installed
on the [Surface Pro 1](https://en.wikipedia.org/wiki/Surface_Pro).

Anyways, I'm sure all the info also likely applies to the Surface Pro 2, but I
cannot test this, as I do not have a Pro 2 device.

The [Linux Surface kernel](https://github.com/linux-surface/linux-surface) is
**not needed** for the touchscreen and stylus to properly function, as indicated
by the [table](https://github.com/linux-surface/linux-surface/wiki/Supported-Devices-and-Features#surface-tablets)
for the Surface tablets.

Though the Surface Pro line uses neither [open source software](https://en.wikipedia.org/wiki/Free_and_open-source_software)
nor [hardware](https://en.wikipedia.org/wiki/Open-source_hardware), I am
outlining my "open as much as possible" approach to successfully running Linux
on the SP1, an `X86_64` device over 9 years old from 2013.

Also, the SP1 is hardly considered [repairable](https://www.ifixit.com/Device/Microsoft_Surface_Pro),
though despite this I'd like to act in accordance with the
[right to repair](https://en.wikipedia.org/wiki/Right_to_repair) movement by
reducing as much electronic waste as possible and take a stand against
[planned obsolescence](https://en.wikipedia.org/wiki/Planned_obsolescence).

I am pretty sure Microsoft wanted to forget that the Surface Pro 1 and 2 even
existed, since these devices were hardly given a warm welcome to Windows 10
(that is, unless you used an online Microsoft account) by the time the
Surface Pro 4 came around.

There might be 1 more file about "extra" packages for Debian-/Ubuntu-based
installs on better hardware in the future, but what's listed here is at least
95% "there" to completion, in line with the [Pareto principle](https://en.wikipedia.org/wiki/Pareto_principle).

All I know is that I will never try to make my own distro with Debian Unstable
and have a result result worse than what "online experts" will ever say about
Manjaro... I'd expect much better results for my first ever DIY Arch Linux
install with [`archinstall`](https://wiki.archlinux.org/title/Archinstall) than
a Universe's lifetime of using Debian Unstable for a laptop.

Plain Debian for servers?  Great.

But plain Debian for desktop?  Never again -- I'd rather install plain Ubuntu
again with its weird [eCryptfs](https://en.wikipedia.org/wiki/ECryptfs) setup
["thing"](https://askubuntu.com/questions/1092277/what-is-home-ecryptfs-and-why-does-it-take-up-so-much-space)
that once killed my Ubuntu install because I deleted it without thinking about
any potential consequences.

## Date

May 29, 2022
