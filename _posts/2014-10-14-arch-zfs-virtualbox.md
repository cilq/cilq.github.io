---
published: false
---

## Arch linux on zfs running native and inside Virtualbox
__In order to move away from Mac OS I use Arch Linux on my work notebook - that's what happens when you want it when you are forced to run windows as well

- setup
- problems in vbox
- problems reach regular install (mkinitcpi in virtualbox?)
- diagnose (import -d /dev/sda, import -d /dev/disk ... -> clean /dev/disk/by-id, zpool import -R /new_root, fail with kernel parameter zfs=rpool, redoing arch zfs wiki entry, forum hint -> could not mount '' -> empty string -> zpool.cache in initramfs
- fix (mkinitramfs -> copy to efi -> vbox crash -> rescue boot -> copy -> works
- next steps


