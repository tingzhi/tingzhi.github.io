---
layout: post
title: Arch Linux Installation Walkthrough
---

## Environment

### 1 VM on Proxmox VE

- 2 cores CPU
- 512M RAM
- 10GB HD

## Instructions

### Verify the boot mode

```
# ls /sys/firmware/efi/efivars
```

### Check Internet connection

```
# ping archlinux.org
```

### Update the system clock

```
# timedatectl set-ntp true
```

#### Adjust the time zone to Pacific

```
# timedatectl list-timezones
# timedatectl set-timezone America/Los_Angelos
```

### Partition the disks

#### List the devices

```
# fdisk -l 
```

#### Partition

```
# fdisk /dev/sda
```

Inside fdisk prompt, the commands are the following:

- **p** print the partition table
- **n** create a new partition


- **d** delete a partition
- **q** quit without saving changes
- **w** write the new partition table and exit

Just follow the instructions and I made one partition for the root directory.

#### Format the partition

```
# mkfs.ext4 /dev/sda1
```

#### Mount the file systems

```
# mount /dev/sda1 /mnt
```

### Install the base packages

```
# pacstrap /mnt base
```

### Configure the system

#### Fstab & Chroot

```
# genfstab -U /mnt >> /mnt/etc/fstab
# arch-chroot /mnt
```

### Time zone

#### Set the time zone:

```
# ln -s /usr/share/zoneinfo/Region/City /etc/localtime
```

### Locale

```
# locale-gen
# nano /etc/locale.conf
LANG=en_US.UTF-8
```

### Hostname

```
# nano /etc/hostname
coolarch
# nano /etc/hosts
127.0.0.1	coolarch.localdomain	coolarch
```

### Set root password

```
# passwd
```

### Boot loader

I chose GRUB (GRand Unified Bootloader)

```
# pacman -S grub
# grub-install --target=i386-pc /dev/sda
# grub-mkconfig -o /boot/grub/grub.cfg
```

### Reboot

Exit the chroot environment, unmount all the partitions, and restart the computer.

```
# exit
# umount -R /mnt
# reboot
```

------

After restart the machine, you should be able to login into the new system with the root account.



### Reference

[Arch Linux Installation Guide](https://wiki.archlinux.org/index.php/Installation_guide#Update_the_system_clock)

[fdisk](http://www.tldp.org/HOWTO/Partition/fdisk_partitioning.html)