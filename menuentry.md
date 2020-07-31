# Add menuentry

```bash
# list disk
~ sudo fdisk -l

Disk /dev/sda: 250.1 GB, 250059350016 bytes, 488397168 sectors
Units = sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disk label type: dos
Disk identifier: 0x2cf68995

   Device Boot      Start         End      Blocks   Id  System
/dev/sda1   *        2048      206847      102400    7  HPFS/NTFS/exFAT
/dev/sda2          206848   167856127    83824640    7  HPFS/NTFS/exFAT
/dev/sda3       167856128   404467711   118305792    7  HPFS/NTFS/exFAT
/dev/sda4       404467712   488396799    41964544    5  Extended
/dev/sda5       404469760   406566911     1048576   83  Linux
/dev/sda6       406568960   488396799    40913920   8e  Linux LVM

# edit the menuentry -- you have to be root
~ su
Password: 

> vim /etc/grub.d/40_custom
```

From the `{bash} fdisk -l` above we know that Windows 7 are located on `/dev/sda2` hence the partition will be `hd0,1` with a = 0, 2 = 1 or first disk, 2nd partition. 

```bash
#!/bin/sh
exec tail -n +3 $0
# This file provides an easy way to add custom menu entries.  Simply type the
# menu entries you want to add after this comment.  Be careful not to change
# the 'exec tail' line above.

menuentry "Windows 7" {
        set root=(hd0,1)
        chainloader +1
}

```

We now run the follwing command to apply new changes to `grub.cfg` file:

```bash
~ grub2-mkconfig --ouput=/boot/grub2/grub.cfg

Found [...]
Found [...]
[...]
done
```

Reboot the system and you\'ll see the effect.

```bash
reboot
```
