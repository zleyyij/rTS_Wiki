---
layout: default
title: ddrescue Usage
nav_exclude: false
has_children: false
parent: Disks
search_exclude: false
last_modified_date: 2022-08-03
---
# ddrescue Usage

This article relies on the live media [created here](/docs/live-sessions/linux-live-session)

GNU ddrescue is a data recovery tool. It copies data from one file or block device (hard disc, cdrom, etc) to another, trying to rescue the good parts first in case of read errors.

## Using ddrescue to image a disk.
### Pre-Requisites
1. Basic terminal knowledge.
2. Basic understanding of disk layouts.
3. Basic understading of disk mounting in Linux.
4. A second disk of equal or larger size to hold the image created by ddrescue. 
    * It is assumed to be mounted at `/mnt/disk` before step 1.

### Steps
1. In a terminal run `lsblk` to output the current disks seen by the machine. Identify the disk you want to operate on based on size and partition layout.
    > If you do not know how to open a terminal, the goals of this guide are likely too advanced.

    ![ddrescue-lsblk.png](/assets/ddrescue/ddrescue-lsblk.png)

2. `ddrescue -d -r3 /dev/sdX /mnt/disk/recovered.dd recovered.log`
    > This writes our image file to `/mnt/disk` and outputs a log to the current directory. `-d` tells ddrescue to use direct disk access and ignore the kernel’s cache. `-r3` tells ddrescue to retry bad sectors 3 times before giving up.

    > ❗ dd has no progress meter. You will know it completed when it moves to a new line.

## Mounting and viewing data on a ddrescue image.
1. `sudo mount -o loop /mnt/disk/recovered.dd /mnt/image`

Once mounted you can explore the recovered filesystem via the file explorer, assuming the filesystem was stable before imaging.
