beadm
=====

Linux port of a FreeBSD utility to manage Boot Environments on ZFS filesystems from here [link](https://github.com/vermaden/beadm)

**DISCLAIMER: Limited testing, not recommended for production use without further testing - Use at own risk**

This script manages boot enviroment datasets and manipulates the bootfs zfs property, so requires that the boot system read the bootfs zfs property to decide on what dataset to boot. 

Porting notes
-------------

- Removed FreeBSD version check
- Manipulations of zpool.cache were changed from /boot/zfs/zpool.cache to /etc/zfs/zpool.cache 
- Removed adjustments to loader.conf and loader.conf.local
- Changed path of config file from /usr/local/etc/beadm.conf to /etc/beadm.conf
- Changed to GNU date command
- When activating a dataset, set mountpoint to legacy rather than "/"
- Adjusted beadm mount command to return temporary mount path for use with scripting

Testing
-------

Limited, against a single system: grub + dracut + gentoo.

### Tested against: ###

- awk - GNU Awk 4.0.2
- sh - bash 4.2.53(1) (invoked via /bin/sh)
- zfs - zfsonlinux 0.6.4
