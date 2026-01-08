# AMD ROCm OpenCL Runtime for Void Linux

**This template is based on https://aur.archlinux.org/packages/opencl-amd by
luciddream.**

## Installation

Prepare [void-packages](https://github.com/void-linux/void-packages):

```sh
$ git clone https://github.com/void-linux/void-packages --depth 1
$ cd void-packages
$ ./xbps-src binary-bootstrap
$ cd ..
```

Clone the repository:

```sh
$ git clone https://github.com/lnkrr/void-amd-opencl && cd void-amd-opencl
```

Copy the `srcpkg`:

```sh
$ cp -r srcpkgs/amd-opencl ../void-packages/srcpkgs
```

Build:

```sh
$ cd ../void-packages
$ ./xbps-src pkg amd-opencl
```

Install:

```sh
$ sudo xbps-install -R hostdir/binpkgs amd-opencl
```

Reboot and verify:

```sh
$ rocminfo
```

## Installation (via [xbps-extra](https://github.com/lnkrr/xbps-extra))

```sh
$ xbps-extra https://github.com/lnkrr/void-amd-opencl amd-opencl
```

## Running DaVinci Resolve

Install the dependencies:

```sh
$ sudo xbps-install -Su glib pango
```

Run:

```sh
$ LD_PRELOAD="/usr/lib/libglib-2.0.so \
    /usr/lib/libpango-1.0.so.0 \
    /usr/lib/libgio-2.0.so \
    /usr/lib/libgmodule-2.0.so" /opt/resolve/bin/resolve
```

## Running Ollama

RX 6600:

```sh
$ HSA_OVERRIDE_GFX_VERSION=10.3.0 ollama serve
```
