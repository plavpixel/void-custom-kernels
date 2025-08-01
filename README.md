
# Void Linux Custom Kernels

This repository contains the XBPS source packages to build custom Linux kernels for Void Linux, such as `linux-zen`, `linux-tkg`, and others.

For more information, including detailed instructions, creating custom pkgs like these, and prerequisites, refer to the [official Void packages repo](https://github.com/void-linux/void-packages).

## Status

- `linux-zen`: Tested and working on `x86_64`
- `linux-tkg`: WIP
- `linux-cachyos`: Planned
- `linux-liquorix`: Planned

## Known Issues

Thankfully none!

## Credits

See [LICENSE](https://github.com/plavpixel/void-custom-kernels/blob/master/LICENSE).  Additional big thanks to [jmboris and their linux-zen template](https://github.com/jmboris/voidlinux-kernel-zen-6.12.6) for the inspiration.

## Prebuilt Bins

Built `.xbps` packages will occasionally be uploaded to [Releases](https://github.com/plavpixel/void-custom-kernels/releases) when I have the time.


## Quick start

Clone the `void-custom-kernels` git repository:

```
$ git clone https://github.com/plavpixel/void-custom-kernels.git
$ cd void-custom-kernels
```
Install the bootstrap packages:
```
$ ./xbps-src binary-bootstrap
```

Build a package by specifying the `pkg` target and the package name:

```
$ ./xbps-src pkg <package_name>
```

Use `./xbps-src -h` to list all available targets and options.

To build packages marked as 'restricted', modify `etc/conf`:

```
$ echo XBPS_ALLOW_RESTRICTED=yes >> etc/conf
```

Once built, the package will be available in `hostdir/binpkgs` or an appropriate subdirectory (e.g. `hostdir/binpkgs/nonfree`). To install the package:

```
# xbps-install --repository hostdir/binpkgs <package_name>
```

Alternatively, packages can be installed with the `xi` utility, from the `xtools` package. `xi` takes the repository of the current working directory into account.

```
$ xi <package_name>
```
## Contributing
No plans yet to submit PRs to upstream. These templates are sloppy, anyone is welcome to improve them!
