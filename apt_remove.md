# APT packages to remove

Remove these automatically installed packages:
```
$ sudo apt remove \
libreoffice-help-de libreoffice-help-en-gb libreoffice-help-es libreoffice-help-fr libreoffice-help-it   libreoffice-help-ja libreoffice-help-pt libreoffice-help-pt-br libreoffice-help-ru libreoffice-help-zh-cn libreoffice-help-zh-tw \
libreoffice-l10n-ar libreoffice-l10n-de libreoffice-l10n-en-gb libreoffice-l10n-en-za libreoffice-l10n-es libreoffice-l10n-fr libreoffice-l10n-it libreoffice-l10n-ja libreoffice-l10n-pt libreoffice-l10n-pt-br libreoffice-l10n-ru libreoffice-l10n-zh-cn libreoffice-l10n-zh-tw \
hunspell-ar hunspell-de-at-frami hunspell-de-ch-frami hunspell-de-de-frami hunspell-en-au hunspell-en-ca hunspell-en-gb hunspell-en-za hunspell-es hunspell-fr-classical hunspell-fr hunspell-it hunspell-pt-br hunspell-pt-pt hunspell-ru \
hyphen-de hyphen-en-ca hyphen-en-gb hyphen-es hyphen-fr hyphen-it hyphen-pt-br hyphen-pt-pt hyphen-ru \
geary totem com.github.donadigo.eddy 
```

Here's the 1-liner:
```
$ sudo apt remove libreoffice-help-de libreoffice-help-en-gb libreoffice-help-es libreoffice-help-fr libreoffice-help-it   libreoffice-help-ja libreoffice-help-pt libreoffice-help-pt-br libreoffice-help-ru libreoffice-help-zh-cn libreoffice-help-zh-tw libreoffice-l10n-ar libreoffice-l10n-de libreoffice-l10n-en-gb libreoffice-l10n-en-za libreoffice-l10n-es libreoffice-l10n-fr libreoffice-l10n-it libreoffice-l10n-ja libreoffice-l10n-pt libreoffice-l10n-pt-br libreoffice-l10n-ru libreoffice-l10n-zh-cn libreoffice-l10n-zh-tw hunspell-ar hunspell-de-at-frami hunspell-de-ch-frami hunspell-de-de-frami hunspell-en-au hunspell-en-ca hunspell-en-gb hunspell-en-za hunspell-es hunspell-fr-classical hunspell-fr hunspell-it hunspell-pt-br hunspell-pt-pt hunspell-ru hyphen-de hyphen-en-ca hyphen-en-gb hyphen-es hyphen-fr hyphen-it hyphen-pt-br hyphen-pt-pt hyphen-ru geary totem com.github.donadigo.eddy
```
Most are related to LibreOffice localization (i.e., translation) packages.

However, most of my current computer work is limited to the [Anglosphere](https://en.wikipedia.org/wiki/Anglosphere)
(at least for LibreOffice), so I'd like to remove unnecessary localization packages.

I'm not a minimalist computer processor and RAM optimizing try-hard, though I do
like the small amounts of time saved whenever LibreOffice updates come through
via APT for Debian-/Ubuntu-based distros.

After removing these, updating Pop!\_OS once a week on the weekends is a quick
breeze and so much better than what I remember from Ubuntu.

The rest are unnecessary GNOME packages (which System76 luckily removed the
majority of, many which are tediously impossible to remove in vanilla Debian --
I'm looking at you, Evolution; and only the most reasonable ones with no
dependency hell are left) and [Eddy](https://github.com/donadigo/eddy)
preinstalled as an ElementaryOS replacement for [gdebi](https://tracker.debian.org/pkg/gdebi).

(I think Pop!\_Shop is also based on the ElementaryOS app shop?)

