# Third-party APT repos

Always check to make sure instructions are up to date!

* [Brave Browser](https://brave.com/linux/#release-channel-installation)
* [Signal Desktop](https://www.signal.org/download/linux/)
* [`makedeb`](https://www.makedeb.org/) for [MPR](https://mpr.makedeb.org/)
    * [Instructions](https://docs.makedeb.org/installing/apt-repository/)
    * This is used to install [ElectronMail](https://mpr.makedeb.org/packages/electronmail-bin) as 1 official Linux [method](https://github.com/vladimiry/ElectronMail#download)
* Tor Browser
    * [FAQ](https://support.torproject.org/apt/)
    * [Instructions](https://support.torproject.org/apt/tor-deb-repo/)
        * Install these 2 packages: `torbrowser-launcher deb.torproject.org-keyring`
* [Keybase](https://keybase.io/docs/the_app/install_linux)
    * [Code signing key](https://book.keybase.io/docs/server/our-code-signing-key)
        * Download `code_signing_key.asc` from [raw source](https://keybase.io/docs/server_security/code_signing_key.asc)
        * Import with `$ gpg --import code_signing_key.asc`
    * Download [detached signature](https://prerelease.keybase.io/keybase_amd64.deb.sig) `keybase_amd64.deb.sig` for DEB
    * GPG verify (without Web of Trust) with `$ gpg --verify keybase_amd64.deb.sig`
        * The security/threat model isn't as tight as Qubes OS, but this'll have to do
* [LibreWolf](https://librewolf.net/installation/debian/)
* [IVPN](https://www.ivpn.net/apps-linux/#ubuntu)

## Not actively used anymore

* Wire's [Download page](https://wire.com/en/download/)
    * [Instructions](https://github.com/wireapp/wire-desktop/wiki/How-to-install-Wire-for-Desktop-on-Linux) are very easy to miss...

[//]: # (May 23, 2022)
