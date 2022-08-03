---
layout: default
title: Data Retrieval
nav_exclude: false
has_children: false
parent: Disks
search_exclude: false
last_modified_date: 2022-08-01
---

# Data Retrieval
Data recovery is a senstive process that should not be rushed. Review all available options before taking an action, during this time it is recommended to leave the drive powered off and in a safe, cool, dry place. To start the process review the following flowchart that has available options.

![image3](/assets/data-recovery/data-flow-chart.webp)

## From a readable disk using a Linux Live Session
This section relies on the live media [created here](/docs/live-sessions/linux-live-session)

Open the File Manager from the applications menu, you should see your disk in the pane on the left. In the below image, it is the "11GB Volume"

![image1](/assets/data-recovery/dr0.png)

Double click the desired disk and it should open in the file manager.

![image2](/assets/data-recovery/dr1.png)

Once opened, you can drag and drop files to another disk that you mount into the system just like in Windows.

## Cloning Software

Before starting data recovery on a damage disk, it is important to clone the disk to a new one. This will help avoid causing additional damage to the original disk.

For functional disks we recommend [use CloneZilla]() but for disks that show issues you should [use ddrescue](/docs/disks/ddrescue).

## Recovery Software

Once you have a cloned disk, or if the data isn't very important and you decide to recover directly from the damage disk, there are many options for recovery software.

### R-Studio
We recommend a paid software called R-Studio Pro.

You can use the software for free to run a scan on the disk, which generally gives you a decent idea of the possibility of file recovery.

Once you have a scan completed, you can then back up the scan data and purchase the full software, then load the scan data back in and start the recovery process.

[R-Studio Website](https://www.r-studio.com/)

### Testdisk

This is usually reserved for software/virus issues that cause partition table damage in order to recover partitions or a partition table.

[Using Testdisk to recover partition tables](https://www.howtoforge.com/data_recovery_with_testdisk)

## Professional Data Recovery

There are many companies out there that will attempt a recovery for you. 

If your data is very important, we recommend that you contact one of them to get a quote. We are unable to currently recommend any specific companies, so please do your research.

[old wiki article](https://www.reddit.com/r/techsupport/wiki/livelinuxsession#wiki_recover_data_from_your_storage_drives)
