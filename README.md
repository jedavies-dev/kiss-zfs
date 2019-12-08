# ZFS on KISS Linux

## What is this?
This repo contains KISS build files for ZFS on Linux.  Package contains userland utilities and kernel modules.

## How to install?
1. Clone this repo to your machine
2. Add to your KISS_PATH
3. kiss b zfs
4. kiss i zfs

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
