# ZFS on KISS Linux

## What is this?
This repo contains KISS build files for ZFS on Linux.  Package contains userland utilities and kernel modules.  It also contains the ZFS event daemon (zed).
**By using this repo you agree to the patching of the source code during the build process to enable loading of the CDDL-licensed kernel module.**
  Note that there are [licensing differences between the Linux kernel and the ZFS kernel modules](https://www.softwarefreedom.org/resources/2016/linux-kernel-cddl.html).
  
## How to install?
1. Enable the [community repository](https://k1ss.org/install#11.0) on your machine.
2. Clone this repo to your machine.
3. Add it to your KISS_PATH
4. kiss b zfs
5. kiss i zfs

## How to use?
`sudo modprobe zfs`
  
...or to have this happen automatically on system startup, add this to your /etc/inittab:

`::once:/bin/modprobe zfs`

You can then use the zfs tools (zpool, zfs etc.) as normal.

## How to import a pool at boot time?
Add this to your /etc/inittab:

`::once:/usr/bin/zpool import mypool`

## Notes
When you build the package, it builds the kernel modules against your current kernel.  So if you upgrade your kernel, you need to rebuild this package.
