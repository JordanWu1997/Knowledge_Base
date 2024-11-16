# Linux Journey - Journeyman

- Reference
  - https://linuxjourney.com/
  - https://linuxjourney.com/lesson/dev-directory
  - https://linuxjourney.com/lesson/filesystem-hierarchy
  - https://linuxjourney.com/lesson/boot-process-overview

# Table of Contents

- [Linux Journey - Journeyman](#linux-journey---journeyman)
- [Context](#context)
  - [Devices](#devices)
    - [Device Types:](#device-types)
    - [Device Names](#device-names)
    - [/dev (device directory)](#dev-device-directory)
    - [/sys (sysfs)](#sys-sysfs)
    - [udev](#udev)
    - [lsusb, lspci, lsscsi](#lsusb-lspci-lsscsi)
    - [dd](#dd)
  - [The Filesystem](#the-filesystem)
    - [Filesystem Hierarchy](#filesystem-hierarchy)
    - [Filesystem Types](#filesystem-types)
    - [Anatomy of a Disk](#anatomy-of-a-disk)
    - [Disk and Filesystem](#disk-and-filesystem)
  - [Boot the System](#boot-the-system)
    - [Boot Process Overview](#boot-process-overview)
    - [Process: BIOS](#process-bios)
    - [Process: Bootloader](#process-bootloader)
    - [Process: Kernel](#process-kernel)
    - [Process: Init](#process-init)
  - [Process Utilization](#process-utilization)
  - [System Logging](#system-logging)

Created by [gh-md-toc](https://github.com/ekalinin/github-markdown-toc)

# Context

## Devices

### Device Types:

- character (labeled as `c`)
  - Devices that transfer data, but one character at a time
  - Pseudo devices, not physically connected
- block (labeled as `b`)
  - Devices that transfer data, but in large blocks
  - e.g. hard drives, file systems, and etc.
- pipe (labeled as `p`)
  - Allow two or more process to communicate with each other
  - Similar to character devices, but they sends data to processes than devices
- socket (labeled as `s`)
  - Facilitate communication between processes
  - Similar to pipe devices, but they can communicate with many processes at once

### Device Names

- SCSI Devices (pronounced "scuzzy")
  - Devices that uses SCSI protocol
    - e.g. printer, storage, and etc.
  - SCSI: Small Computer System Interface
    - Protocols used for communication between peripherals
  - e.g. `/dev/sda`, `/dev/sda1`
- Pseudo Devices
  - Most common pseudo devices are character devices
  - e.g.
    - `/dev/zero`: Accept and discard all input, produces a continuous steam of NULL (zero value) bytes
    - `/dev/null`: Accept and discard all input, produces no output
    - `/dev/random`: Produce random numbers
- PATA Devices
  - Hard drives in older system
  - e.g. `/dev/hda`, `/dev/hda1`

### /dev (device directory)

- `/dev`: Directory that store device files
- `ls -l /dev`: List all devices, contains
  - Permissions
  - Owner
  - Group
  - Major Device Number
    - Represent the driver that is used
    - e.g. `8` represents sd block devices
  - Minor Device Number
    - Tell kernel which unique device it is in this driver class
    - e.g. `0` represents the first device (a)
  - Timestamp
  - Device name
- Used to allow other programs to access devices

### /sys (sysfs)

- `sysfs` is virtual filesystem, most often mounted to `/sys`
- Used to view information and manager the device

### udev

- Dynamically creates and remove devices
- `udevd`: Daemon for udev, use information stored in `/etc/udev/rules.d/`
- `udevadm`: Command to view the udev database and sysfs
  - Usage: `udevadm info --query=all --name=/dev/sda`

### lsusb, lspci, lsscsi

- `lsusb`: List all USB devices
- `lspci`: List all PCI devices
- `lsscsi`: List SCSI devices

### dd

- Read input from a file or data stream and writes it to a file or data steam
- `dd` options
  - `if=file`: Input file, read from a file
  - `of=file`: Output file, write to a file
  - `bs=bytes`: Block size, it reads and writes this many bytes of data at a time
    - use `k` for kilobyte, `m` for megabyte
  - `count=number`: Number of blocks to copy
- Usage: `dd if=/home/pete/backup.img of=/dev/sdb bs=1M count=2`

## The Filesystem

### Filesystem Hierarchy

### Filesystem Types

- Virtual File System (VFS) abstraction layer
  - Layer between applications and different filesystem types
  - Let applications work across filesystem types
- Journaling
  - Default on most filesystem types
  - Record filesytem task in log file to keep filesystem consistent
- Common Desktop Filesystem Types
  - `ext4`
  - `Btrfs`
  - `XFS`
  - `NTFS` and `FAT`
  - `HFS+`

### Anatomy of a Disk

- Partition Table
  - Tell the system how the disk is partitioned (start and end)
  - `sudo parted -l`: Check partition table
  - Schemes
    - Master Boot Record (MBR)
    - GUID Partition Table (GPT)
- MBR vs GPT
  - `MBR`:
    - Traditional partition table
    - Partition in type of primary (limit to four), extended (limit to one) and logical partitions
    - Add additional partition
      1. Make primary partition into and extended partition
      2. Inside extended partition, add logical partition (which works like other partitions)
    - Only support disks up to 2 TB
  - `GPT`:
    - New standar partion table
    - Only one type and of partition with no number limit
    - Each partition has a globally unique ID (GUID)
    - Mostly used in UEFI based booting
- Filesystem Structure
  - `Boot block`
    - Located in the first few sectors of the filesystem
    - Contains information used to boot the OS.
  - `Super block`
    - Comes after boot block, contains information about the filesystem
  - `Inode table`
    - Database that manages files
  - `Data block`
    - Actual data for files and directories

### Disk and Filesystem

- Disk Partitioning Tool
  - `fdisk`
  - `parted`
  - `gparted`
  - `gdisk`
- Creating Filesystems
  - `mkfs`: make filesystem
- Mount/Umount Filesystem
  - `mount -t `
  - `umount`
- Check Disk Usage
  - `du -hs`
  - `df -h`
- Device UUID: Device Universal Unique ID
  - `blkid`
- Mount Filesystem After Startup: `/etc/fstab`
  - `fstab` (Filesystem table), contains list of filesystem that are mounted
  - For each mounted filesystem, contains
    - `UUID`: Device ID
    - `Mount Point`: Directory the filesystem is mounted to
    - `Filesystem Type`: e.g ext4
    - `Options`: Mount options
    - `Dump`: Used by `dump` to decide when to make backup
    - `Pass`: Used by `fsck` to decide what order filesystem should be check
      - Set value to `0` to be ignored by `fsck`
- Check Consistency of Filesystem
  - `fsck`: Filesystem check
- Inodes: Index Nodes
  - Describe everything about file (e.g. filetype, owner, and etc.)
  - `df -i`: Check inodes on system
  - `ls -li`: Show inodes information of files
  - `stat`: Show detailed information about inode
- Inodes for File links
  - Symlinks: Create new inodes for link (`ln -s`)
  - Hardlinks: Use the same inodes for link (`ln`)

## Boot the System

### Boot Process Overview

- Overview of Linux boot process
  1. `BIOS`
  2. `Bootloader`
  3. `Kernel`
  4. `Init`

### Process: BIOS

- Main goal
  - Find the system bootloader
- Basic Input/Output System (BIOS)
  - Perform system integrity checks
  - Search for the boot block to figure out how to boot up the system
- Unified extensible firmware interface (UEFI)
  - Successor of BIOS

### Process: Bootloader

- Main goal
  - Boot into an OS (not specified to linux OS)
  - Select a kernel to use
  - Specify kernel parameters
- GRUB
  - Common bootloader for linux, contains parameters
    - `initrd`: Specify the location of initial RAM disk
    - `BOOT_IMAGE`: Where the kernel image is located
    - `root`: Location of the root filesystem
    - `ro`: Mount the filesystem as read-only mode
    - `quiet`: Stop displaying messages that going on in the background during boot
    - `splash`: Let splash screen be shown

### Process: Kernel

- Main goal
  - Bootup kernel
  - Mount the root filesystem
- Chicken (kernel) and egg (filesystem) problem
  - Kernel manage hardware, however not all drivers are available to kernel during bootup. Therefore, a temporary filesystem with all necessary drivers is needed
- To Bootup kernel:
  - Old days: Mount `initrd` (initial ram disk) as temporary filesystem
  - Nowadays: Use `initramfs`, temporary root filesystem that is built into the kernel
- Mount the root filesystem
  - At first, kernel create a root device and mount the root partition in read-only mode
  - After fsck for system integrity, it remounts root filesystem in read-write mode

### Process: Init

- Main goal
  - Get essential services start on system
- System V init (sysv)
  - Traditional init system
  - Sequentially starts and stop processes based on startup scripts
- Upstart:
  - Jobs and events
  - Start jobs that performs certain action in response to events
  - Can be found in older Ubuntu installations
- Systemd:
  - New standard for init
  - Goal orientated
  - If there is a goal, it tries to complete the dependencies of the goal to complete the goal

## Process Utilization

## System Logging
