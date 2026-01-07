# AMD ROCm OpenCL Runtime for Void Linux

**This template is based on https://aur.archlinux.org/packages/opencl-amd by
luciddream.**

## Installation

Prepare [void-packages](https://github.com/void-linux/void-packages):

```sh
git clone https://github.com/void-linux/void-packages --depth 1
cd void-packages
./xbps-src binary-bootstrap
cd ..
```

Clone the repository:

```sh
git clone https://github.com/lnkrr/void-amd-opencl && cd void-amd-opencl
```

Copy the `srcpkg`:

```sh
cp -r srcpkgs/amd-opencl ../void-packages/srcpkgs
```

Build:

```sh
cd ../void-packages
./xbps-src pkg amd-opencl
```

Install:

```sh
sudo xbps-install -R hostdir/binpkgs amd-opencl
```

Reboot and verify:

```sh
rocminfo
```
