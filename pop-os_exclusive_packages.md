# Pop!\_OS exclusive packages

Currently I only need the Keyboard Configurator [application](https://system76.com/accessories/launch/download)
for the System76 [Launch Keyboard](https://system76.com/accessories/launch).

There are no instructions on how to install the application via the CLI and I
serendipitously stumbled upon this with `$ apt search system76 keyboard`.

```
$ sudo apt install system76-keyboard-configurator
```

The support [page](https://support.system76.com/articles/launch-keyboard/) lists
what's in the box of every box of each Launch Keyboard.

The technical documentation gives a self-contained [look](https://tech-docs.system76.com/models/launch_1/external-overview.html)
and no marketing pizzazz from the product page (as if the marketing was even
self-gratuitous in the first place) and [details](https://tech-docs.system76.com/models/launch_1/repairs.html)
on how to basically disassemble the Launch Keyboard.

Lastly, the GitHub [repo](https://github.com/system76/launch) for the mechanical
and PCB designs are not to be confused with the repo for the Keyboard
Configurator application [itself](https://github.com/pop-os/keyboard-configurator).

