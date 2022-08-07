---
layout: default
title: Using Clonezilla
nav_exclude: false
has_children: false
parent: Disks
search_exclude: false
last_modified_date: 2022-08-07
---

# Using Clonezilla

This article relies on the live media [created here](/docs/live-sessions/linux-live-session)

## Launching Clonezilla
In the Linux live session, open a Terminal from the menu and run `sudo clonezilla`.

![clonezilla-main](/assets/clonezilla/clonezilla-main.png)

## Creating a disk image
These steps are for writing to a local device, but the tool can also be used for writing to remote servers (via SSH/SMB/NFS/etc).

1. Choose "device-image"
2. Choose "local_dev". You are now prompted to insert any media that you want to store the image on.

    ![clonezilla-local-dev](/assets/clonezilla/clonezilla-local-dev.png)

3. Clonezilla lists all devices and asks where to store the image being made.

    ![clonezilla-local-dev](/assets/clonezilla/clonezilla-storage-sel.png)
    Select the location to STORE the image, not the disk that we are making an image of.

4. You are asked where to store the image on the chosen disk. You can navigate the file structure by pressing "Enter" on any folder.

    ![clonezilla-folder0](/assets/clonezilla/clonezilla-folder0.png)
    ![clonezilla-folder1](/assets/clonezilla/clonezilla-folder1.png)

    If you do not have a folder created you can create one in another terminal with the command `sudo mkdir /tmp/ocsroot_bind_root/Image_Destination`, then refresh the view of the disk with the "Browse" option.
    When you have the correct destination selected, cycle to "Done" to continue.

5. Choose "Beginner"

    ![clonezilla-level](/assets/clonezilla/clonezilla-level.png)

6. Choose "savedisk", if you want to image specific partitions that is outside the scope of this guide.

    ![clonezilla-level](/assets/clonezilla/clonezilla-save-type.png)

7. Provide a file name for your image

    ![clonezilla-name](/assets/clonezilla/clonezilla-name.png)

8. Choose which disks you want to take an image of. You can identify your disk based on size and possibly by label.

    ![clonezilla-disk-sel](/assets/clonezilla/clonezilla-disk-sel.png)

9. Leave the compression method as default.

    ![clonezilla-compression](/assets/clonezilla/clonezilla-compression.png)

10. Skip the disk check and use the default option that Clonezilla provides. This is fine in most cases.

    ![clonezilla-fs-check](/assets/clonezilla/clonezilla-fs-check.png)

11. Checking the image is the default and is encouraged. Disable it if you want to save time.

    ![clonezilla-integrity](/assets/clonezilla/clonezilla-integrity.png)

12. Encrypting the image is not withing the scope of this guide, but is possible.

    ![clonezilla-encryption](/assets/clonezilla/clonezilla-encryption.png)

13. Leaving the default for the final action will allow you to see the results, and continue without needlessly rebooting.

    ![clonezilla-reboot](/assets/clonezilla/clonezilla-reboot.png)

14. You will see a summary of the command that will be run. Press "enter" to continue.

    ![clonezilla-confirmation](/assets/clonezilla/clonezilla-confirmation.png)

15. The last step before writing our image is the summary page. Make sure that everything is correct, then type "y" and hit "enter".

    ![clonezilla-summary](/assets/clonezilla/clonezilla-summary.png)

16. When it is done you will be left with a success message. Press "enter" to finish and fall back to a commandline.

    ![clonezilla-finished](/assets/clonezilla/clonezilla-finished.png)

In the output directory you chose in step 4, you will now see a directory with the name you picked in step 7. Inside the directory are many files which together are a Clonezilla compatible image.

## Mounting a Clonezilla image
To do any work on your image it, will need to be mounted like a drive. To do this, we will convert the output files from above into a single file that can be mounted.

Notes:
* Our image was compressed with gzip by default and this guide expects that default was used.
* By default Clonezilla seems to use `/tmp/ocsroot_bind_root` as the mountpoint of its storage drive. If you are using our guide straight through this directory should work. If it does not or if you are using an image created at another time then replace that path with your own.
* We are writing our image to the same disk that it is already stored on. This will need up to 2x the original disk worth of space to succeed. If you do not have enough space on the original storage disk you may require a second.
* We are running all commands in this section as root. `sudo su` is required to get us into the root user.

```bash
sudo su
cat /tmp/ocsroot_bind_root/Image_Destination/Image_Name/*img.gz.* | gunzip | partclone.restore --restore_raw_file -C -s - -o /tmp/ocsroot_bind/Image_Destination/Disk.img

mount /tmp/ocsroot_bind_root/Image_DestinationDisk.img /mnt
```
